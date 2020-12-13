---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Frame para CustomItem para CustomControl para View (formato)
description: Elemento Frame para CustomItem para CustomControl para View (formato)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652194"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="60e13-103">Elemento Frame para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="60e13-103">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="60e13-104">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="60e13-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="60e13-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="60e13-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="60e13-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento de quadro CustomControlView (Format) para CustomItem para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="60e13-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="60e13-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="60e13-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="60e13-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="60e13-108">Attributes and Elements</span></span>

<span data-ttu-id="60e13-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="60e13-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="60e13-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="60e13-110">Attributes</span></span>

<span data-ttu-id="60e13-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="60e13-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="60e13-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="60e13-112">Child Elements</span></span>

|<span data-ttu-id="60e13-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="60e13-113">Element</span></span>|<span data-ttu-id="60e13-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="60e13-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="60e13-115">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="60e13-115">Required Element</span></span>|
|[<span data-ttu-id="60e13-116">Elemento FirstLineHanging</span><span class="sxs-lookup"><span data-stu-id="60e13-116">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="60e13-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="60e13-117">Optional element.</span></span><br /><br /> <span data-ttu-id="60e13-118">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="60e13-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="60e13-119">Elemento FirstLineIndent</span><span class="sxs-lookup"><span data-stu-id="60e13-119">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="60e13-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="60e13-120">Optional element.</span></span><br /><br /> <span data-ttu-id="60e13-121">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="60e13-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="60e13-122">Elemento LeftIndent</span><span class="sxs-lookup"><span data-stu-id="60e13-122">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="60e13-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="60e13-123">Optional element.</span></span><br /><br /> <span data-ttu-id="60e13-124">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="60e13-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="60e13-125">Elemento RightIndent</span><span class="sxs-lookup"><span data-stu-id="60e13-125">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="60e13-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="60e13-126">Optional element.</span></span><br /><br /> <span data-ttu-id="60e13-127">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="60e13-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="60e13-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="60e13-128">Parent Elements</span></span>

|<span data-ttu-id="60e13-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="60e13-129">Element</span></span>|<span data-ttu-id="60e13-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="60e13-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60e13-131">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="60e13-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="60e13-132">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="60e13-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="60e13-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="60e13-133">Remarks</span></span>

<span data-ttu-id="60e13-134">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) no mesmo `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="60e13-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="60e13-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60e13-135">See Also</span></span>

[<span data-ttu-id="60e13-136">Elemento FirstLineHanging</span><span class="sxs-lookup"><span data-stu-id="60e13-136">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="60e13-137">Elemento FirstLineIndent</span><span class="sxs-lookup"><span data-stu-id="60e13-137">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="60e13-138">Elemento LeftIndent</span><span class="sxs-lookup"><span data-stu-id="60e13-138">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="60e13-139">Elemento RightIndent</span><span class="sxs-lookup"><span data-stu-id="60e13-139">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="60e13-140">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="60e13-140">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="60e13-141">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="60e13-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
