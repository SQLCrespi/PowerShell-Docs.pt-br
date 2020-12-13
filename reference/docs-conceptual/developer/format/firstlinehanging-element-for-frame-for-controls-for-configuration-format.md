---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FirstLineHanging para Frame para Controls para Configuration (formato)
description: Elemento FirstLineHanging para Frame para Controls para Configuration (formato)
ms.openlocfilehash: 94d59ef7b54e036f76e38a3b06b769700443b9fb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655237"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="28b77-103">Elemento FirstLineHanging para Frame para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="28b77-103">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="28b77-104">Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="28b77-104">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="28b77-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="28b77-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="28b77-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento de quadro de configuração para CustomItem para controles para o elemento de configuração (Format) FirstLineHanging para frame para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="28b77-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="28b77-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="28b77-107">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28b77-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="28b77-108">Attributes and Elements</span></span>

<span data-ttu-id="28b77-109">As seções a seguir descrevem atributos, elementos filho e elemento pai do `FirstLineHanging` elemento.</span><span class="sxs-lookup"><span data-stu-id="28b77-109">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="28b77-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="28b77-110">Attributes</span></span>

<span data-ttu-id="28b77-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="28b77-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28b77-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="28b77-112">Child Elements</span></span>

<span data-ttu-id="28b77-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="28b77-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="28b77-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="28b77-114">Parent Elements</span></span>

|<span data-ttu-id="28b77-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="28b77-115">Element</span></span>|<span data-ttu-id="28b77-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="28b77-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28b77-117">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="28b77-117">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="28b77-118">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="28b77-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="28b77-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="28b77-119">Text Value</span></span>

<span data-ttu-id="28b77-120">Especifique o número de caracteres que você deseja que a primeira linha dos dados seja deslocada.</span><span class="sxs-lookup"><span data-stu-id="28b77-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="28b77-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="28b77-121">Remarks</span></span>

<span data-ttu-id="28b77-122">Se esse elemento for especificado, você não poderá especificar o `FirstLineIndent` elemento.</span><span class="sxs-lookup"><span data-stu-id="28b77-122">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="28b77-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28b77-123">See Also</span></span>

[<span data-ttu-id="28b77-124">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="28b77-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="28b77-125">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="28b77-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
