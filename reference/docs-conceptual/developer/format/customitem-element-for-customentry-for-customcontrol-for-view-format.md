---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomItem para CustomEntry para CustomControl para View (formato)
description: Elemento CustomItem para CustomEntry para CustomControl para View (formato)
ms.openlocfilehash: 9090a3ada5316ba5ddb4a9c46eee37c11982ae6e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666732"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="adf54-103">Elemento CustomItem para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-103">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="adf54-104">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="adf54-104">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="adf54-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="adf54-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="adf54-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="adf54-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="adf54-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="adf54-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="adf54-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="adf54-108">Attributes and Elements</span></span>

<span data-ttu-id="adf54-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="adf54-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="adf54-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="adf54-110">Attributes</span></span>

<span data-ttu-id="adf54-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="adf54-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="adf54-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="adf54-112">Child Elements</span></span>

|<span data-ttu-id="adf54-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="adf54-113">Element</span></span>|<span data-ttu-id="adf54-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="adf54-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="adf54-115">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-115">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="adf54-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="adf54-116">Optional element.</span></span><br /><br /> <span data-ttu-id="adf54-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="adf54-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="adf54-118">Elemento Frame para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-118">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="adf54-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="adf54-119">Optional element.</span></span><br /><br /> <span data-ttu-id="adf54-120">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="adf54-120">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="adf54-121">Elemento de nova linha para CustomItem para controle personalizado para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-121">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="adf54-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="adf54-122">Optional element.</span></span><br /><br /> <span data-ttu-id="adf54-123">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="adf54-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="adf54-124">Elemento de texto para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-124">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="adf54-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="adf54-125">Optional element.</span></span><br /><br /> <span data-ttu-id="adf54-126">Especifica texto adicional para os dados exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="adf54-126">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="adf54-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="adf54-127">Parent Elements</span></span>

|<span data-ttu-id="adf54-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="adf54-128">Element</span></span>|<span data-ttu-id="adf54-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="adf54-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="adf54-130">Elemento CustomEntry para CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-130">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="adf54-131">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="adf54-131">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="adf54-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="adf54-132">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="adf54-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="adf54-133">See Also</span></span>

[<span data-ttu-id="adf54-134">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-134">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="adf54-135">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-135">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="adf54-136">Elemento Frame para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-136">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="adf54-137">Elemento NewLine para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-137">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="adf54-138">Elemento de texto para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="adf54-138">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="adf54-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="adf54-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
