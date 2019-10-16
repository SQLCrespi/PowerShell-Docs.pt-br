---
title: Elemento de quadro para CustomItem para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: 925ef86e61801f5a66f89dd25e0756f00dd35155
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363635"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="f6148-102">Elemento Frame para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="f6148-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="f6148-103">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="f6148-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="f6148-104">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="f6148-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="f6148-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento de quadro CustomControlView (Format) para CustomItem para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="f6148-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f6148-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f6148-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f6148-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f6148-107">Attributes and Elements</span></span>

<span data-ttu-id="f6148-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="f6148-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f6148-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f6148-109">Attributes</span></span>

<span data-ttu-id="f6148-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f6148-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f6148-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="f6148-111">Child Elements</span></span>

|<span data-ttu-id="f6148-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6148-112">Element</span></span>|<span data-ttu-id="f6148-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f6148-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="f6148-114">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="f6148-114">Required Element</span></span>|
|[<span data-ttu-id="f6148-115">Elemento FirstLineHanging</span><span class="sxs-lookup"><span data-stu-id="f6148-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="f6148-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f6148-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f6148-117">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="f6148-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="f6148-118">Elemento FirstLineIndent</span><span class="sxs-lookup"><span data-stu-id="f6148-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="f6148-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f6148-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f6148-120">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="f6148-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="f6148-121">Elemento LeftIndent</span><span class="sxs-lookup"><span data-stu-id="f6148-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="f6148-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f6148-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f6148-123">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="f6148-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="f6148-124">Elemento RightIndent</span><span class="sxs-lookup"><span data-stu-id="f6148-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="f6148-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f6148-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f6148-126">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="f6148-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f6148-127">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="f6148-127">Parent Elements</span></span>

|<span data-ttu-id="f6148-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6148-128">Element</span></span>|<span data-ttu-id="f6148-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="f6148-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f6148-130">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="f6148-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="f6148-131">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="f6148-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f6148-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="f6148-132">Remarks</span></span>

<span data-ttu-id="f6148-133">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) no mesmo elemento `Frame`.</span><span class="sxs-lookup"><span data-stu-id="f6148-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6148-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6148-134">See Also</span></span>

[<span data-ttu-id="f6148-135">Elemento FirstLineHanging</span><span class="sxs-lookup"><span data-stu-id="f6148-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f6148-136">Elemento FirstLineIndent</span><span class="sxs-lookup"><span data-stu-id="f6148-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f6148-137">Elemento LeftIndent</span><span class="sxs-lookup"><span data-stu-id="f6148-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f6148-138">Elemento RightIndent</span><span class="sxs-lookup"><span data-stu-id="f6148-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f6148-139">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="f6148-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f6148-140">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6148-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
