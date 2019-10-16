---
title: Elemento Expand (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368735"
---
# <a name="expand-element-format"></a><span data-ttu-id="0df0e-102">Elemento Expand (formato)</span><span class="sxs-lookup"><span data-stu-id="0df0e-102">Expand Element (Format)</span></span>

<span data-ttu-id="0df0e-103">Especifica como o objeto de coleção é expandido para essa definição.</span><span class="sxs-lookup"><span data-stu-id="0df0e-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="0df0e-104">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion Element (Format) Expand elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="0df0e-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0df0e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0df0e-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0df0e-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0df0e-106">Attributes and Elements</span></span>

<span data-ttu-id="0df0e-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Expand`.</span><span class="sxs-lookup"><span data-stu-id="0df0e-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0df0e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0df0e-108">Attributes</span></span>

<span data-ttu-id="0df0e-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0df0e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0df0e-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="0df0e-110">Child Elements</span></span>

<span data-ttu-id="0df0e-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0df0e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0df0e-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="0df0e-112">Parent Elements</span></span>

|<span data-ttu-id="0df0e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0df0e-113">Element</span></span>|<span data-ttu-id="0df0e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="0df0e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0df0e-115">Elemento EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0df0e-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="0df0e-116">Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0df0e-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0df0e-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0df0e-117">Text Value</span></span>

<span data-ttu-id="0df0e-118">Especifique um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="0df0e-118">Specify one of the following values:</span></span>

- <span data-ttu-id="0df0e-119">EnumOnly: exibe somente as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="0df0e-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="0df0e-120">CoreOnly: exibe somente as propriedades do objeto de coleção.</span><span class="sxs-lookup"><span data-stu-id="0df0e-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="0df0e-121">Ambos: exibe as propriedades dos objetos na coleção e as propriedades do objeto da coleção.</span><span class="sxs-lookup"><span data-stu-id="0df0e-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0df0e-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="0df0e-122">Remarks</span></span>

<span data-ttu-id="0df0e-123">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="0df0e-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="0df0e-124">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="0df0e-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="0df0e-125">O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="0df0e-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="0df0e-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0df0e-126">See Also</span></span>

[<span data-ttu-id="0df0e-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0df0e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
