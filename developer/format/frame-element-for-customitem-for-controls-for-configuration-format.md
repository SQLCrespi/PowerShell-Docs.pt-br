---
title: Elemento de quadros para CustomItem para controles de configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065553"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="f0cf4-102">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f0cf4-103">Define como os dados são exibidos, como o deslocamento de dados para a esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="f0cf4-104">Esse elemento é usado durante a definição de um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f0cf4-105">Elemento de controles de (formato) do elemento de configuração do elemento de controle de configuração (formato) para controles para o elemento de CustomControl de configuração (formato) para o controle para o elemento de configuração (formato) de CustomEntries para CustomControl para configuração ( Elemento de CustomEntry Format) para CustomControl controles para o elemento de configuração (formato) de CustomItem para CustomEntry controles para o elemento de quadro de configuração para CustomItem para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f0cf4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f0cf4-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f0cf4-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="f0cf4-107">Attributes and Elements</span></span>

<span data-ttu-id="f0cf4-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0cf4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0cf4-109">Attributes</span></span>

<span data-ttu-id="f0cf4-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f0cf4-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f0cf4-111">Child Elements</span></span>

|<span data-ttu-id="f0cf4-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0cf4-112">Element</span></span>|<span data-ttu-id="f0cf4-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0cf4-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="f0cf4-114">Elemento necessário</span><span class="sxs-lookup"><span data-stu-id="f0cf4-114">Required Element</span></span>|
|[<span data-ttu-id="f0cf4-115">Elemento FirstLineHanging de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="f0cf4-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f0cf4-117">Especifica quantos caracteres, a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="f0cf4-118">Elemento FirstLineIndent de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="f0cf4-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f0cf4-120">Especifica quantos caracteres, a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="f0cf4-121">Elemento LeftIndent de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="f0cf4-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f0cf4-123">Especifica o número de caracteres de dados são deslocados da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="f0cf4-124">Elemento RightIndent de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="f0cf4-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f0cf4-126">Especifica o número de caracteres de dados são deslocados da margem direita.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f0cf4-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f0cf4-127">Parent Elements</span></span>

|<span data-ttu-id="f0cf4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0cf4-128">Element</span></span>|<span data-ttu-id="f0cf4-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0cf4-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f0cf4-130">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="f0cf4-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="f0cf4-131">Define quais dados são exibidos pelo controle e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f0cf4-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="f0cf4-132">Remarks</span></span>

<span data-ttu-id="f0cf4-133">Não é possível especificar o [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) e o [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elementos no mesmo `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0cf4-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f0cf4-134">See Also</span></span>

[<span data-ttu-id="f0cf4-135">Elemento FirstLineHanging de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0cf4-136">Elemento FirstLineIndent de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0cf4-137">Elemento LeftIndent de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0cf4-138">Elemento RightIndent de quadro para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f0cf4-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0cf4-139">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="f0cf4-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0cf4-140">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0cf4-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
