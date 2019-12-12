---
title: Elemento ScriptBlock para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364925"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="596e3-102">Elemento ScriptBlock para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="596e3-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="596e3-103">Especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="596e3-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="596e3-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) ScriptBlock para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="596e3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="596e3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="596e3-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="596e3-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="596e3-106">Attributes and Elements</span></span>

<span data-ttu-id="596e3-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="596e3-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="596e3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="596e3-108">Attributes</span></span>

<span data-ttu-id="596e3-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="596e3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="596e3-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="596e3-110">Child Elements</span></span>

<span data-ttu-id="596e3-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="596e3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="596e3-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="596e3-112">Parent Elements</span></span>

|<span data-ttu-id="596e3-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="596e3-113">Element</span></span>|<span data-ttu-id="596e3-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="596e3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="596e3-115">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="596e3-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="596e3-116">Define como um grupo de objetos .NET é exibido.</span><span class="sxs-lookup"><span data-stu-id="596e3-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="596e3-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="596e3-117">Text Value</span></span>

<span data-ttu-id="596e3-118">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="596e3-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="596e3-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="596e3-119">Remarks</span></span>

<span data-ttu-id="596e3-120">O PowerShell inicia um novo grupo sempre que o valor desse script é alterado.</span><span class="sxs-lookup"><span data-stu-id="596e3-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="596e3-121">Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](propertyname-element-for-groupby-format.md) para iniciar um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="596e3-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="596e3-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="596e3-122">See Also</span></span>

[<span data-ttu-id="596e3-123">Elemento PropertyName para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="596e3-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="596e3-124">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="596e3-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="596e3-125">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="596e3-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
