---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomItem para CustomEntry para GroupBy (formato)
description: Elemento CustomItem para CustomEntry para GroupBy (formato)
ms.openlocfilehash: 5db23ad4dad5bd66ea64b9c6e91b8224a4aa4eca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645980"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="1693d-103">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-103">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="1693d-104">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="1693d-104">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="1693d-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="1693d-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1693d-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomItem Element para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1693d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1693d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1693d-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1693d-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1693d-108">Attributes and Elements</span></span>

<span data-ttu-id="1693d-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="1693d-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1693d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1693d-110">Attributes</span></span>

<span data-ttu-id="1693d-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="1693d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1693d-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1693d-112">Child Elements</span></span>

|<span data-ttu-id="1693d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1693d-113">Element</span></span>|<span data-ttu-id="1693d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="1693d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1693d-115">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-115">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="1693d-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1693d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="1693d-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="1693d-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="1693d-118">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-118">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="1693d-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1693d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="1693d-120">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="1693d-120">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="1693d-121">Elemento NewLine para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-121">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="1693d-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1693d-122">Optional element.</span></span><br /><br /> <span data-ttu-id="1693d-123">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="1693d-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="1693d-124">Elemento Text para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-124">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="1693d-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1693d-125">Optional element.</span></span><br /><br /> <span data-ttu-id="1693d-126">Especifica texto adicional para os dados exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="1693d-126">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1693d-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1693d-127">Parent Elements</span></span>

|<span data-ttu-id="1693d-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1693d-128">Element</span></span>|<span data-ttu-id="1693d-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="1693d-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1693d-130">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-130">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="1693d-131">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="1693d-131">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1693d-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="1693d-132">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="1693d-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1693d-133">See Also</span></span>

[<span data-ttu-id="1693d-134">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-134">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="1693d-135">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-135">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="1693d-136">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-136">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="1693d-137">Elemento NewLine para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-137">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="1693d-138">Elemento Text para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1693d-138">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="1693d-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1693d-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
