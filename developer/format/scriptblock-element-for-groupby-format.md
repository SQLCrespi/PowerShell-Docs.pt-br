---
title: Elemento ScriptBlock para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229307"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="e3961-102">Elemento ScriptBlock para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="e3961-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="e3961-103">Especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="e3961-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="e3961-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) ScriptBlock elemento GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="e3961-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3961-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e3961-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3961-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e3961-106">Attributes and Elements</span></span>

<span data-ttu-id="e3961-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="e3961-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3961-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3961-108">Attributes</span></span>

<span data-ttu-id="e3961-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e3961-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3961-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="e3961-110">Child Elements</span></span>

<span data-ttu-id="e3961-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e3961-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3961-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="e3961-112">Parent Elements</span></span>

|<span data-ttu-id="e3961-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3961-113">Element</span></span>|<span data-ttu-id="e3961-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3961-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3961-115">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e3961-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="e3961-116">Define como um grupo de objetos do .NET é exibido.</span><span class="sxs-lookup"><span data-stu-id="e3961-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e3961-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="e3961-117">Text Value</span></span>

<span data-ttu-id="e3961-118">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="e3961-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3961-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="e3961-119">Remarks</span></span>

<span data-ttu-id="e3961-120">PowerShell inicia um novo grupo sempre que o valor desse script é alterado.</span><span class="sxs-lookup"><span data-stu-id="e3961-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="e3961-121">Quando esse elemento for especificado, é possível especificar o [PropertyName](propertyname-element-for-groupby-format.md) elemento para iniciar um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="e3961-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3961-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3961-122">See Also</span></span>

[<span data-ttu-id="e3961-123">Elemento PropertyName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="e3961-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="e3961-124">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e3961-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="e3961-125">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3961-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
