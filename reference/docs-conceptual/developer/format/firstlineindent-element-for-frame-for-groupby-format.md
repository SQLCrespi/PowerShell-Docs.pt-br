---
title: Elemento FirstLineIndent para frame para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33be3b9e-53c8-433f-8c11-c65b0d46744c
caps.latest.revision: 6
ms.openlocfilehash: 9ba6fc1b9924a4b0d5b56ee15290a2293217403c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363075"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="5dc29-102">Elemento FirstLineIndent para Frame para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="5dc29-102">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="5dc29-103">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="5dc29-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="5dc29-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="5dc29-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5dc29-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) CustomItem elemento para CustomEntry para o elemento de quadro GroupBy (Format) para CustomItem para o elemento de FirstLineIndent GroupBy (Format) para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dc29-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5dc29-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5dc29-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5dc29-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5dc29-107">Attributes and Elements</span></span>

<span data-ttu-id="5dc29-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `FirstLineIndent`.</span><span class="sxs-lookup"><span data-stu-id="5dc29-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5dc29-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5dc29-109">Attributes</span></span>

<span data-ttu-id="5dc29-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5dc29-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5dc29-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="5dc29-111">Child Elements</span></span>

<span data-ttu-id="5dc29-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5dc29-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5dc29-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="5dc29-113">Parent Elements</span></span>

|<span data-ttu-id="5dc29-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="5dc29-114">Element</span></span>|<span data-ttu-id="5dc29-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5dc29-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5dc29-116">Elemento frame para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dc29-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="5dc29-117">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="5dc29-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5dc29-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="5dc29-118">Text Value</span></span>

<span data-ttu-id="5dc29-119">Especifique o número de caracteres que você deseja que a primeira linha dos dados seja deslocada.</span><span class="sxs-lookup"><span data-stu-id="5dc29-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="5dc29-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="5dc29-120">Remarks</span></span>

<span data-ttu-id="5dc29-121">Se esse elemento for especificado, você não poderá especificar o elemento [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="5dc29-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dc29-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5dc29-122">See Also</span></span>

[<span data-ttu-id="5dc29-123">Elemento FirstLineHanging para frame para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dc29-123">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="5dc29-124">Elemento frame para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dc29-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="5dc29-125">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dc29-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
