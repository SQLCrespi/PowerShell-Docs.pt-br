---
title: Elemento de quadro para CustomItem para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065590"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="307b9-102">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="307b9-103">Define como os dados são exibidos, como o deslocamento de dados para a esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="307b9-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="307b9-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="307b9-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="307b9-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) CustomItem CustomEntry para elemento de quadro GroupBy (formato) CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="307b9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="307b9-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="307b9-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="307b9-107">Attributes and Elements</span></span>

<span data-ttu-id="307b9-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="307b9-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="307b9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="307b9-109">Attributes</span></span>

<span data-ttu-id="307b9-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="307b9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="307b9-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="307b9-111">Child Elements</span></span>

|<span data-ttu-id="307b9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="307b9-112">Element</span></span>|<span data-ttu-id="307b9-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="307b9-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="307b9-114">Elemento necessário</span><span class="sxs-lookup"><span data-stu-id="307b9-114">Required Element</span></span>|
|[<span data-ttu-id="307b9-115">Elemento FirstLineHanging para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="307b9-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="307b9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="307b9-117">Especifica quantos caracteres, a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="307b9-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="307b9-118">Elemento FirstLineIndent para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="307b9-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="307b9-119">Optional element.</span></span><br /><br /> <span data-ttu-id="307b9-120">Especifica quantos caracteres, a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="307b9-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="307b9-121">Elemento LeftIndent para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="307b9-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="307b9-122">Optional element.</span></span><br /><br /> <span data-ttu-id="307b9-123">Especifica o número de caracteres de dados são deslocados da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="307b9-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="307b9-124">[Elemento RightIndent para quadro de GroupBy (formato)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent elemento</span><span class="sxs-lookup"><span data-stu-id="307b9-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="307b9-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="307b9-125">Optional element.</span></span><br /><br /> <span data-ttu-id="307b9-126">Especifica o número de caracteres de dados são deslocados da margem direita.</span><span class="sxs-lookup"><span data-stu-id="307b9-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="307b9-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="307b9-127">Parent Elements</span></span>

|<span data-ttu-id="307b9-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="307b9-128">Element</span></span>|<span data-ttu-id="307b9-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="307b9-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="307b9-130">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="307b9-131">Define quais dados são exibidos pelo controle e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="307b9-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="307b9-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="307b9-132">Remarks</span></span>

<span data-ttu-id="307b9-133">Não é possível especificar o [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) e o [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elementos no mesmo `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="307b9-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="307b9-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="307b9-134">See Also</span></span>

[<span data-ttu-id="307b9-135">Elemento FirstLineHanging para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="307b9-136">Elemento FirstLineIndent para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="307b9-137">Elemento LeftIndent para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="307b9-138">Elemento RightIndent para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="307b9-139">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="307b9-140">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="307b9-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
