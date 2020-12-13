---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para GroupBy (formato)
description: Elemento ScriptBlock para GroupBy (formato)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665243"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="630fd-103">Elemento ScriptBlock para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="630fd-103">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="630fd-104">Especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="630fd-104">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="630fd-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) ScriptBlock para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="630fd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="630fd-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="630fd-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="630fd-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="630fd-107">Attributes and Elements</span></span>

<span data-ttu-id="630fd-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="630fd-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="630fd-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="630fd-109">Attributes</span></span>

<span data-ttu-id="630fd-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="630fd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="630fd-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="630fd-111">Child Elements</span></span>

<span data-ttu-id="630fd-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="630fd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="630fd-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="630fd-113">Parent Elements</span></span>

|<span data-ttu-id="630fd-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="630fd-114">Element</span></span>|<span data-ttu-id="630fd-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="630fd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="630fd-116">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="630fd-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="630fd-117">Define como um grupo de objetos .NET é exibido.</span><span class="sxs-lookup"><span data-stu-id="630fd-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="630fd-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="630fd-118">Text Value</span></span>

<span data-ttu-id="630fd-119">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="630fd-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="630fd-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="630fd-120">Remarks</span></span>

<span data-ttu-id="630fd-121">O PowerShell inicia um novo grupo sempre que o valor desse script é alterado.</span><span class="sxs-lookup"><span data-stu-id="630fd-121">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="630fd-122">Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](propertyname-element-for-groupby-format.md) para iniciar um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="630fd-122">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="630fd-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="630fd-123">See Also</span></span>

[<span data-ttu-id="630fd-124">Elemento PropertyName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="630fd-124">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="630fd-125">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="630fd-125">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="630fd-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="630fd-126">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
