---
title: Elemento FirstLineIndent para quadro de GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33be3b9e-53c8-433f-8c11-c65b0d46744c
caps.latest.revision: 6
ms.openlocfilehash: 9ba6fc1b9924a4b0d5b56ee15290a2293217403c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065834"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="636f6-102">Elemento FirstLineIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="636f6-102">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="636f6-103">Especifica quantos caracteres, a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="636f6-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="636f6-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="636f6-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="636f6-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) CustomItem CustomEntry para elemento de quadro GroupBy (formato) CustomItem para elemento GroupBy (formato) FirstLineIndent de quadro para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="636f6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="636f6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="636f6-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="636f6-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="636f6-107">Attributes and Elements</span></span>

<span data-ttu-id="636f6-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `FirstLineIndent` elemento.</span><span class="sxs-lookup"><span data-stu-id="636f6-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="636f6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="636f6-109">Attributes</span></span>

<span data-ttu-id="636f6-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="636f6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="636f6-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="636f6-111">Child Elements</span></span>

<span data-ttu-id="636f6-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="636f6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="636f6-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="636f6-113">Parent Elements</span></span>

|<span data-ttu-id="636f6-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="636f6-114">Element</span></span>|<span data-ttu-id="636f6-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="636f6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="636f6-116">Elemento de quadro para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="636f6-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="636f6-117">Define como os dados são exibidos, como o deslocamento de dados para a esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="636f6-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="636f6-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="636f6-118">Text Value</span></span>

<span data-ttu-id="636f6-119">Especifique o número de caracteres que você deseja deslocar a primeira linha dos dados.</span><span class="sxs-lookup"><span data-stu-id="636f6-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="636f6-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="636f6-120">Remarks</span></span>

<span data-ttu-id="636f6-121">Se esse elemento for especificado, não é possível especificar o [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="636f6-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="636f6-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="636f6-122">See Also</span></span>

[<span data-ttu-id="636f6-123">Elemento FirstLineHanging para quadro de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="636f6-123">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="636f6-124">Elemento de quadro para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="636f6-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="636f6-125">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="636f6-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
