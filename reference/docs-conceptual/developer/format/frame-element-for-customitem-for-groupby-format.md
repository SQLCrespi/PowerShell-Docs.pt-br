---
title: Elemento frame para CustomItem para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1568236ff7b6142f7e41be70a3ae5e28307cf790
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785754"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="fb5c4-102">Elemento Frame para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="fb5c4-103">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="fb5c4-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="fb5c4-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries de GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento CustomItem de GroupBy (Format) para CustomEntry para o elemento de quadro GroupBy (Format) para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fb5c4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fb5c4-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fb5c4-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fb5c4-107">Attributes and Elements</span></span>

<span data-ttu-id="fb5c4-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fb5c4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fb5c4-109">Attributes</span></span>

<span data-ttu-id="fb5c4-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fb5c4-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="fb5c4-111">Child Elements</span></span>

|<span data-ttu-id="fb5c4-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb5c4-112">Element</span></span>|<span data-ttu-id="fb5c4-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="fb5c4-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="fb5c4-114">Elemento obrigatório</span><span class="sxs-lookup"><span data-stu-id="fb5c4-114">Required Element</span></span>|
|[<span data-ttu-id="fb5c4-115">Elemento FirstLineHanging para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="fb5c4-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-116">Optional element.</span></span><br /><br /> <span data-ttu-id="fb5c4-117">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="fb5c4-118">Elemento FirstLineIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="fb5c4-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-119">Optional element.</span></span><br /><br /> <span data-ttu-id="fb5c4-120">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="fb5c4-121">Elemento LeftIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="fb5c4-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-122">Optional element.</span></span><br /><br /> <span data-ttu-id="fb5c4-123">Especifica quantos caracteres os dados são deslocados para fora da margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="fb5c4-124">[Elemento RightIndent para frame para GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Elemento RightIndent</span><span class="sxs-lookup"><span data-stu-id="fb5c4-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="fb5c4-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-125">Optional element.</span></span><br /><br /> <span data-ttu-id="fb5c4-126">Especifica quantos caracteres os dados são deslocados para fora da margem direita.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fb5c4-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="fb5c4-127">Parent Elements</span></span>

|<span data-ttu-id="fb5c4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb5c4-128">Element</span></span>|<span data-ttu-id="fb5c4-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="fb5c4-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fb5c4-130">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="fb5c4-131">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fb5c4-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="fb5c4-132">Remarks</span></span>

<span data-ttu-id="fb5c4-133">Você não pode especificar os elementos [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) e [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) no mesmo `Frame` elemento.</span><span class="sxs-lookup"><span data-stu-id="fb5c4-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb5c4-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb5c4-134">See Also</span></span>

[<span data-ttu-id="fb5c4-135">Elemento FirstLineHanging para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="fb5c4-136">Elemento FirstLineIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="fb5c4-137">Elemento LeftIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="fb5c4-138">Elemento RightIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="fb5c4-139">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fb5c4-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="fb5c4-140">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb5c4-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
