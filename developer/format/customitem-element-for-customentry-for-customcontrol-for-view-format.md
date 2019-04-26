---
title: Elemento CustomItem para CustomEntry para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066395"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="5acf1-102">Elemento CustomItem para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="5acf1-103">Define quais dados são exibidos com o modo de exibição do controle personalizado e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="5acf1-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="5acf1-104">Esse elemento é usado ao definir uma exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="5acf1-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="5acf1-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento CustomControl (formato) CustomEntries elemento de configuração para CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para elemento CustomItem de exibição (formato) CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5acf1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5acf1-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5acf1-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="5acf1-107">Attributes and Elements</span></span>

<span data-ttu-id="5acf1-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="5acf1-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5acf1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5acf1-109">Attributes</span></span>

<span data-ttu-id="5acf1-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5acf1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5acf1-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5acf1-111">Child Elements</span></span>

|<span data-ttu-id="5acf1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5acf1-112">Element</span></span>|<span data-ttu-id="5acf1-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5acf1-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5acf1-114">Elemento ExpressionBinding para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="5acf1-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5acf1-115">Optional element.</span></span><br /><br /> <span data-ttu-id="5acf1-116">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="5acf1-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="5acf1-117">Elemento de quadro para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="5acf1-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5acf1-118">Optional element.</span></span><br /><br /> <span data-ttu-id="5acf1-119">Define quais dados são exibidos com o modo de exibição do controle personalizado e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="5acf1-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="5acf1-120">Elemento de nova linha para CustomItem para um controle personalizado para o modo de exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="5acf1-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5acf1-121">Optional element.</span></span><br /><br /> <span data-ttu-id="5acf1-122">Adiciona uma linha em branco para a exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="5acf1-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="5acf1-123">Elemento de texto para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="5acf1-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5acf1-124">Optional element.</span></span><br /><br /> <span data-ttu-id="5acf1-125">Especifica o texto adicional para os dados exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="5acf1-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5acf1-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5acf1-126">Parent Elements</span></span>

|<span data-ttu-id="5acf1-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="5acf1-127">Element</span></span>|<span data-ttu-id="5acf1-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="5acf1-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5acf1-129">Elemento CustomEntry para CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="5acf1-130">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="5acf1-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5acf1-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="5acf1-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="5acf1-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5acf1-132">See Also</span></span>

[<span data-ttu-id="5acf1-133">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5acf1-134">Elemento ExpressionBinding para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5acf1-135">Elemento de quadro para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5acf1-136">Elemento de nova linha para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5acf1-137">Elemento de texto para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5acf1-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="5acf1-138">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5acf1-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
