---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Frame para CustomItem para GroupBy (formato)
description: Elemento Frame para CustomItem para GroupBy (formato)
ms.openlocfilehash: 86b51766974ebfcae06583ade237a77c6db92866
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652174"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="f3328-103">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-103">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="f3328-104">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="f3328-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="f3328-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="f3328-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f3328-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries de GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento CustomItem de GroupBy (Format) para CustomEntry para o elemento de quadro GroupBy (Format) para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f3328-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f3328-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f3328-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f3328-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f3328-108">Attributes and Elements</span></span>

<span data-ttu-id="f3328-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="f3328-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f3328-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f3328-110">Attributes</span></span>

<span data-ttu-id="f3328-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f3328-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f3328-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f3328-112">Child Elements</span></span>

|<span data-ttu-id="f3328-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3328-113">Element</span></span>|<span data-ttu-id="f3328-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3328-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="f3328-115">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="f3328-115">Required Element</span></span>|
|[<span data-ttu-id="f3328-116">Elemento FirstLineHanging para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-116">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="f3328-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f3328-117">Optional element.</span></span><br /><br /> <span data-ttu-id="f3328-118">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="f3328-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="f3328-119">Elemento FirstLineIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-119">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="f3328-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f3328-120">Optional element.</span></span><br /><br /> <span data-ttu-id="f3328-121">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="f3328-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="f3328-122">Elemento LeftIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-122">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="f3328-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f3328-123">Optional element.</span></span><br /><br /> <span data-ttu-id="f3328-124">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="f3328-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="f3328-125">[Elemento RightIndent para frame para GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Elemento RightIndent</span><span class="sxs-lookup"><span data-stu-id="f3328-125">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="f3328-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f3328-126">Optional element.</span></span><br /><br /> <span data-ttu-id="f3328-127">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="f3328-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f3328-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f3328-128">Parent Elements</span></span>

|<span data-ttu-id="f3328-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3328-129">Element</span></span>|<span data-ttu-id="f3328-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3328-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3328-131">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-131">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="f3328-132">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="f3328-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f3328-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="f3328-133">Remarks</span></span>

<span data-ttu-id="f3328-134">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) no mesmo `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="f3328-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3328-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3328-135">See Also</span></span>

[<span data-ttu-id="f3328-136">Elemento FirstLineHanging para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-136">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="f3328-137">Elemento FirstLineIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-137">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="f3328-138">Elemento LeftIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-138">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="f3328-139">Elemento RightIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-139">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="f3328-140">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f3328-140">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="f3328-141">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3328-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
