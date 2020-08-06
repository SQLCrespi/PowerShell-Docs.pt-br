---
title: Elemento CustomItem para CustomEntry para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783714"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="26ed8-102">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="26ed8-103">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="26ed8-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="26ed8-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="26ed8-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="26ed8-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomItem Element para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="26ed8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="26ed8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="26ed8-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="26ed8-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="26ed8-107">Attributes and Elements</span></span>

<span data-ttu-id="26ed8-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="26ed8-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="26ed8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="26ed8-109">Attributes</span></span>

<span data-ttu-id="26ed8-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="26ed8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="26ed8-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="26ed8-111">Child Elements</span></span>

|<span data-ttu-id="26ed8-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="26ed8-112">Element</span></span>|<span data-ttu-id="26ed8-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="26ed8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26ed8-114">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="26ed8-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="26ed8-115">Optional element.</span></span><br /><br /> <span data-ttu-id="26ed8-116">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="26ed8-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="26ed8-117">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="26ed8-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="26ed8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="26ed8-119">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="26ed8-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="26ed8-120">Elemento NewLine para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="26ed8-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="26ed8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="26ed8-122">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="26ed8-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="26ed8-123">Elemento Text para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="26ed8-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="26ed8-124">Optional element.</span></span><br /><br /> <span data-ttu-id="26ed8-125">Especifica texto adicional para os dados exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="26ed8-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="26ed8-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="26ed8-126">Parent Elements</span></span>

|<span data-ttu-id="26ed8-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="26ed8-127">Element</span></span>|<span data-ttu-id="26ed8-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="26ed8-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26ed8-129">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="26ed8-130">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="26ed8-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="26ed8-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="26ed8-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="26ed8-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26ed8-132">See Also</span></span>

[<span data-ttu-id="26ed8-133">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="26ed8-134">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="26ed8-135">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="26ed8-136">Elemento NewLine para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="26ed8-137">Elemento Text para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="26ed8-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="26ed8-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="26ed8-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
