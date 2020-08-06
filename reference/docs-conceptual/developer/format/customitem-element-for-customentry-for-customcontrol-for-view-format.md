---
title: Elemento CustomItem para CustomEntry para CustomControl para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 25101c9c156ef91657f51db7044bf9a6653142a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785822"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="796ab-102">Elemento CustomItem para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="796ab-103">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="796ab-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="796ab-104">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="796ab-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="796ab-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="796ab-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="796ab-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="796ab-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="796ab-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="796ab-107">Attributes and Elements</span></span>

<span data-ttu-id="796ab-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="796ab-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="796ab-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="796ab-109">Attributes</span></span>

<span data-ttu-id="796ab-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="796ab-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="796ab-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="796ab-111">Child Elements</span></span>

|<span data-ttu-id="796ab-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="796ab-112">Element</span></span>|<span data-ttu-id="796ab-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="796ab-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="796ab-114">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="796ab-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="796ab-115">Optional element.</span></span><br /><br /> <span data-ttu-id="796ab-116">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="796ab-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="796ab-117">Elemento Frame para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="796ab-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="796ab-118">Optional element.</span></span><br /><br /> <span data-ttu-id="796ab-119">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="796ab-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="796ab-120">Elemento de nova linha para CustomItem para controle personalizado para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="796ab-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="796ab-121">Optional element.</span></span><br /><br /> <span data-ttu-id="796ab-122">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="796ab-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="796ab-123">Elemento de texto para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="796ab-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="796ab-124">Optional element.</span></span><br /><br /> <span data-ttu-id="796ab-125">Especifica texto adicional para os dados exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="796ab-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="796ab-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="796ab-126">Parent Elements</span></span>

|<span data-ttu-id="796ab-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="796ab-127">Element</span></span>|<span data-ttu-id="796ab-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="796ab-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="796ab-129">Elemento CustomEntry para CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="796ab-130">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="796ab-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="796ab-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="796ab-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="796ab-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="796ab-132">See Also</span></span>

[<span data-ttu-id="796ab-133">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="796ab-134">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="796ab-135">Elemento Frame para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="796ab-136">Elemento NewLine para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="796ab-137">Elemento de texto para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="796ab-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="796ab-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="796ab-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
