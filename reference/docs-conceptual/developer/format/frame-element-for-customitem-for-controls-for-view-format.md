---
title: Elemento frame para CustomItem para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363645"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="150c9-102">Elemento Frame para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="150c9-102">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="150c9-103">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="150c9-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="150c9-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="150c9-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="150c9-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento de quadro View (Format) para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="150c9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="150c9-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="150c9-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="150c9-107">Attributes and Elements</span></span>

<span data-ttu-id="150c9-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="150c9-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="150c9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="150c9-109">Attributes</span></span>

<span data-ttu-id="150c9-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="150c9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="150c9-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="150c9-111">Child Elements</span></span>

|<span data-ttu-id="150c9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="150c9-112">Element</span></span>|<span data-ttu-id="150c9-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="150c9-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="150c9-114">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="150c9-114">Required Element</span></span>|
|[<span data-ttu-id="150c9-115">Elemento FirstLineHanging do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-115">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="150c9-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="150c9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="150c9-117">Especifica quantos caracteres a primeira linha é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="150c9-117">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="150c9-118">Elemento FirstLineIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-118">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="150c9-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="150c9-119">Optional element.</span></span><br /><br /> <span data-ttu-id="150c9-120">Especifica quantos caracteres a primeira linha é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="150c9-120">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="150c9-121">Elemento LeftIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-121">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="150c9-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="150c9-122">Optional element.</span></span><br /><br /> <span data-ttu-id="150c9-123">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="150c9-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="150c9-124">Elemento RightIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-124">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="150c9-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="150c9-125">Optional element.</span></span><br /><br /> <span data-ttu-id="150c9-126">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="150c9-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="150c9-127">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="150c9-127">Parent Elements</span></span>

|<span data-ttu-id="150c9-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="150c9-128">Element</span></span>|<span data-ttu-id="150c9-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="150c9-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="150c9-130">Elemento CustomItem para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-130">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="150c9-131">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="150c9-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="150c9-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="150c9-132">Remarks</span></span>

<span data-ttu-id="150c9-133">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) no mesmo elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="150c9-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="150c9-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="150c9-134">See Also</span></span>

[<span data-ttu-id="150c9-135">Elemento FirstLineHanging do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-135">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="150c9-136">Elemento FirstLineIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-136">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="150c9-137">Elemento LeftIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-137">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="150c9-138">Elemento RightIndent do quadro de controles de View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-138">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="150c9-139">Elemento CustomItem para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="150c9-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="150c9-140">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="150c9-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
