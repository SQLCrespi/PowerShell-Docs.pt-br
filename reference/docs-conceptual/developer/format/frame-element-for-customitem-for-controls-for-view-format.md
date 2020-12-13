---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Frame para CustomItem para Controls para View (formato)
description: Elemento Frame para CustomItem para Controls para View (formato)
ms.openlocfilehash: 6f26e19a6894ac213b924108a56cb80f9ffd1143
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652197"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="1e1e3-103">Elemento Frame para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-103">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="1e1e3-104">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="1e1e3-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="1e1e3-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento de quadro View (Format) para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1e1e3-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1e1e3-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e1e3-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1e1e3-108">Attributes and Elements</span></span>

<span data-ttu-id="1e1e3-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e1e3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e1e3-110">Attributes</span></span>

<span data-ttu-id="1e1e3-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e1e3-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1e1e3-112">Child Elements</span></span>

|<span data-ttu-id="1e1e3-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e1e3-113">Element</span></span>|<span data-ttu-id="1e1e3-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e1e3-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="1e1e3-115">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="1e1e3-115">Required Element</span></span>|
|[<span data-ttu-id="1e1e3-116">Elemento FirstLineHanging do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-116">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="1e1e3-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-117">Optional element.</span></span><br /><br /> <span data-ttu-id="1e1e3-118">Especifica quantos caracteres a primeira linha é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-118">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="1e1e3-119">Elemento FirstLineIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-119">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="1e1e3-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-120">Optional element.</span></span><br /><br /> <span data-ttu-id="1e1e3-121">Especifica quantos caracteres a primeira linha é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-121">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="1e1e3-122">Elemento LeftIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-122">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="1e1e3-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-123">Optional element.</span></span><br /><br /> <span data-ttu-id="1e1e3-124">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="1e1e3-125">Elemento RightIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-125">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="1e1e3-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-126">Optional element.</span></span><br /><br /> <span data-ttu-id="1e1e3-127">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1e1e3-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1e1e3-128">Parent Elements</span></span>

|<span data-ttu-id="1e1e3-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e1e3-129">Element</span></span>|<span data-ttu-id="1e1e3-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e1e3-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e1e3-131">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-131">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="1e1e3-132">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1e1e3-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="1e1e3-133">Remarks</span></span>

<span data-ttu-id="1e1e3-134">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) no mesmo `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e1e3-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e1e3-135">See Also</span></span>

[<span data-ttu-id="1e1e3-136">Elemento FirstLineHanging do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-136">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="1e1e3-137">Elemento FirstLineIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-137">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="1e1e3-138">Elemento LeftIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-138">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="1e1e3-139">Elemento RightIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-139">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="1e1e3-140">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-140">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="1e1e3-141">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1e3-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
