---
title: Elemento FirstLineIndent para frame para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec63f4f9-8858-4529-8646-ffbbc278f83e
caps.latest.revision: 7
ms.openlocfilehash: 694c5baaa5e90a772257276ba139d90acf7ec0e3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363085"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="07cc0-102">Elemento FirstLineIndent para Frame para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="07cc0-102">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="07cc0-103">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="07cc0-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="07cc0-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="07cc0-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="07cc0-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento de quadro View (Format) para CustomItem para controles para View (Format) FirstLineIndent elemento of frame de controles de exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="07cc0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineIndent Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="07cc0-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="07cc0-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07cc0-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="07cc0-107">Attributes and Elements</span></span>

<span data-ttu-id="07cc0-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `FirstLineIndent`.</span><span class="sxs-lookup"><span data-stu-id="07cc0-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="07cc0-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="07cc0-109">Attributes</span></span>

<span data-ttu-id="07cc0-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="07cc0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="07cc0-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="07cc0-111">Child Elements</span></span>

<span data-ttu-id="07cc0-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="07cc0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="07cc0-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="07cc0-113">Parent Elements</span></span>

|<span data-ttu-id="07cc0-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="07cc0-114">Element</span></span>|<span data-ttu-id="07cc0-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="07cc0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07cc0-116">Elemento frame para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="07cc0-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="07cc0-117">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="07cc0-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="07cc0-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="07cc0-118">Text Value</span></span>

<span data-ttu-id="07cc0-119">Especifique o número de caracteres que você deseja que a primeira linha dos dados seja deslocada.</span><span class="sxs-lookup"><span data-stu-id="07cc0-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="07cc0-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="07cc0-120">Remarks</span></span>

<span data-ttu-id="07cc0-121">Se esse elemento for especificado, você não poderá especificar o elemento [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="07cc0-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="07cc0-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07cc0-122">See Also</span></span>

[<span data-ttu-id="07cc0-123">Elemento FirstLineHanging para frame para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="07cc0-123">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="07cc0-124">Elemento frame para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="07cc0-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="07cc0-125">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="07cc0-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
