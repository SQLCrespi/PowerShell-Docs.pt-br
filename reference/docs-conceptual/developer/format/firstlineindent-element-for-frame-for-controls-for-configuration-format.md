---
title: Elemento FirstLineIndent para frame para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f489720-11f6-4019-940e-07f423d4278d
caps.latest.revision: 6
ms.openlocfilehash: c5b2d971fe1590116f96b024ae8769334768acf2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363115"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="4182a-102">Elemento FirstLineIndent para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4182a-102">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4182a-103">Especifica quantos caracteres a primeira linha de dados é deslocada para a direita.</span><span class="sxs-lookup"><span data-stu-id="4182a-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="4182a-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="4182a-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4182a-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento de quadro de configuração para CustomItem para controles para o elemento de configuração (Format) FirstLineIndent para frame para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="4182a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4182a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4182a-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4182a-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4182a-107">Attributes and Elements</span></span>

<span data-ttu-id="4182a-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `FirstLineIndent`.</span><span class="sxs-lookup"><span data-stu-id="4182a-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4182a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4182a-109">Attributes</span></span>

<span data-ttu-id="4182a-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4182a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4182a-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="4182a-111">Child Elements</span></span>

<span data-ttu-id="4182a-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4182a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4182a-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="4182a-113">Parent Elements</span></span>

|<span data-ttu-id="4182a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4182a-114">Element</span></span>|<span data-ttu-id="4182a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="4182a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4182a-116">Elemento frame para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4182a-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="4182a-117">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="4182a-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4182a-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="4182a-118">Text Value</span></span>

<span data-ttu-id="4182a-119">Especifique o número de caracteres que você deseja que a primeira linha dos dados seja deslocada.</span><span class="sxs-lookup"><span data-stu-id="4182a-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="4182a-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="4182a-120">Remarks</span></span>

<span data-ttu-id="4182a-121">Se esse elemento for especificado, você não poderá especificar o elemento [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) .</span><span class="sxs-lookup"><span data-stu-id="4182a-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="4182a-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4182a-122">See Also</span></span>

[<span data-ttu-id="4182a-123">Elemento FirstLineHanging para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4182a-123">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4182a-124">Elemento frame para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4182a-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="4182a-125">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4182a-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
