---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Frame para CustomItem para Controls para Configuration (formato)
description: Elemento Frame para CustomItem para Controls para Configuration (formato)
ms.openlocfilehash: 85d095b9b0c25b68b2353bce56b85333aff91b98
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652238"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="4f051-103">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-103">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4f051-104">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="4f051-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="4f051-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="4f051-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4f051-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para os controles do elemento de quadro de configuração para CustomItem para controles para configuração</span><span class="sxs-lookup"><span data-stu-id="4f051-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f051-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4f051-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f051-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4f051-108">Attributes and Elements</span></span>

<span data-ttu-id="4f051-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="4f051-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f051-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f051-110">Attributes</span></span>

<span data-ttu-id="4f051-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="4f051-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f051-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="4f051-112">Child Elements</span></span>

|<span data-ttu-id="4f051-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f051-113">Element</span></span>|<span data-ttu-id="4f051-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="4f051-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="4f051-115">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f051-115">Required Element</span></span>|
|[<span data-ttu-id="4f051-116">Elemento FirstLineHanging para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-116">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4f051-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4f051-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4f051-118">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="4f051-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="4f051-119">Elemento FirstLineIndent para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-119">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4f051-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4f051-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4f051-121">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="4f051-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="4f051-122">Elemento LeftIndent para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-122">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4f051-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4f051-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4f051-124">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="4f051-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="4f051-125">Elemento RightIndent para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-125">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4f051-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4f051-126">Optional element.</span></span><br /><br /> <span data-ttu-id="4f051-127">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="4f051-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4f051-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="4f051-128">Parent Elements</span></span>

|<span data-ttu-id="4f051-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f051-129">Element</span></span>|<span data-ttu-id="4f051-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="4f051-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f051-131">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="4f051-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="4f051-132">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="4f051-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4f051-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="4f051-133">Remarks</span></span>

<span data-ttu-id="4f051-134">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) no mesmo `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="4f051-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f051-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f051-135">See Also</span></span>

[<span data-ttu-id="4f051-136">Elemento FirstLineHanging para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-136">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4f051-137">Elemento FirstLineIndent para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-137">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4f051-138">Elemento LeftIndent para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-138">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4f051-139">Elemento RightIndent para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4f051-139">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4f051-140">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="4f051-140">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="4f051-141">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f051-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
