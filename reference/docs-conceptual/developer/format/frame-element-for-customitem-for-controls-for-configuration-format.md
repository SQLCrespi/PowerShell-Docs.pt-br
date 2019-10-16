---
title: Elemento frame para CustomItem para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363655"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="9ce97-102">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="9ce97-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9ce97-103">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="9ce97-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="9ce97-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="9ce97-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9ce97-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento de quadro de configuração para CustomItem para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="9ce97-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9ce97-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ce97-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9ce97-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9ce97-107">Attributes and Elements</span></span>

<span data-ttu-id="9ce97-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="9ce97-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ce97-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ce97-109">Attributes</span></span>

<span data-ttu-id="9ce97-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9ce97-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9ce97-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="9ce97-111">Child Elements</span></span>

|<span data-ttu-id="9ce97-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ce97-112">Element</span></span>|<span data-ttu-id="9ce97-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ce97-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="9ce97-114">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="9ce97-114">Required Element</span></span>|
|[<span data-ttu-id="9ce97-115">Elemento FirstLineHanging para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="9ce97-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9ce97-116">Optional element.</span></span><br /><br /> <span data-ttu-id="9ce97-117">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="9ce97-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="9ce97-118">Elemento FirstLineIndent para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="9ce97-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9ce97-119">Optional element.</span></span><br /><br /> <span data-ttu-id="9ce97-120">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="9ce97-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="9ce97-121">Elemento LeftIndent para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="9ce97-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9ce97-122">Optional element.</span></span><br /><br /> <span data-ttu-id="9ce97-123">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="9ce97-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="9ce97-124">Elemento RightIndent para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="9ce97-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9ce97-125">Optional element.</span></span><br /><br /> <span data-ttu-id="9ce97-126">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="9ce97-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9ce97-127">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="9ce97-127">Parent Elements</span></span>

|<span data-ttu-id="9ce97-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ce97-128">Element</span></span>|<span data-ttu-id="9ce97-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ce97-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ce97-130">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="9ce97-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="9ce97-131">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="9ce97-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9ce97-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="9ce97-132">Remarks</span></span>

<span data-ttu-id="9ce97-133">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) no mesmo elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="9ce97-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ce97-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ce97-134">See Also</span></span>

[<span data-ttu-id="9ce97-135">Elemento FirstLineHanging para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="9ce97-136">Elemento FirstLineIndent para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="9ce97-137">Elemento LeftIndent para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="9ce97-138">Elemento RightIndent para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="9ce97-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="9ce97-139">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="9ce97-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="9ce97-140">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ce97-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
