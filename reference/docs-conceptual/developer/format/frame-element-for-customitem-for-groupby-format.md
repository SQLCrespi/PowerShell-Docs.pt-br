---
title: Elemento frame para CustomItem para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362945"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="d1fae-102">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d1fae-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="d1fae-103">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="d1fae-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="d1fae-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="d1fae-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d1fae-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) CustomItem elemento para CustomEntry para o elemento de quadro GroupBy (Format) para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d1fae-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d1fae-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d1fae-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d1fae-107">Attributes and Elements</span></span>

<span data-ttu-id="d1fae-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="d1fae-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d1fae-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1fae-109">Attributes</span></span>

<span data-ttu-id="d1fae-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d1fae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d1fae-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="d1fae-111">Child Elements</span></span>

|<span data-ttu-id="d1fae-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1fae-112">Element</span></span>|<span data-ttu-id="d1fae-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="d1fae-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="d1fae-114">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="d1fae-114">Required Element</span></span>|
|[<span data-ttu-id="d1fae-115">Elemento FirstLineHanging para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="d1fae-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1fae-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d1fae-117">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="d1fae-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="d1fae-118">Elemento FirstLineIndent para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="d1fae-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1fae-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d1fae-120">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="d1fae-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="d1fae-121">Elemento LeftIndent para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="d1fae-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1fae-122">Optional element.</span></span><br /><br /> <span data-ttu-id="d1fae-123">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="d1fae-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="d1fae-124">[Elemento RightIndent para frame para GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Elemento RightIndent</span><span class="sxs-lookup"><span data-stu-id="d1fae-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="d1fae-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1fae-125">Optional element.</span></span><br /><br /> <span data-ttu-id="d1fae-126">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="d1fae-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d1fae-127">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="d1fae-127">Parent Elements</span></span>

|<span data-ttu-id="d1fae-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1fae-128">Element</span></span>|<span data-ttu-id="d1fae-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="d1fae-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d1fae-130">Elemento CustomItem para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="d1fae-131">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d1fae-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d1fae-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="d1fae-132">Remarks</span></span>

<span data-ttu-id="d1fae-133">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) no mesmo elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="d1fae-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1fae-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1fae-134">See Also</span></span>

[<span data-ttu-id="d1fae-135">Elemento FirstLineHanging para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d1fae-136">Elemento FirstLineIndent para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d1fae-137">Elemento LeftIndent para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d1fae-138">Elemento RightIndent para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d1fae-139">Elemento CustomItem para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d1fae-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="d1fae-140">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1fae-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
