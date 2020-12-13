---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Expand (formato)
description: Elemento Expand (formato)
ms.openlocfilehash: 518e132e3e74b921d4e51966fc60088a22ef63f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667939"
---
# <a name="expand-element-format"></a><span data-ttu-id="813f2-103">Elemento Expand (formato)</span><span class="sxs-lookup"><span data-stu-id="813f2-103">Expand Element (Format)</span></span>

<span data-ttu-id="813f2-104">Especifica como o objeto de coleção é expandido para essa definição.</span><span class="sxs-lookup"><span data-stu-id="813f2-104">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="813f2-105">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion Element (Format) Expand elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="813f2-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="813f2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="813f2-106">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="813f2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="813f2-107">Attributes and Elements</span></span>

<span data-ttu-id="813f2-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Expand` elemento.</span><span class="sxs-lookup"><span data-stu-id="813f2-108">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="813f2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="813f2-109">Attributes</span></span>

<span data-ttu-id="813f2-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="813f2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="813f2-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="813f2-111">Child Elements</span></span>

<span data-ttu-id="813f2-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="813f2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="813f2-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="813f2-113">Parent Elements</span></span>

|<span data-ttu-id="813f2-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="813f2-114">Element</span></span>|<span data-ttu-id="813f2-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="813f2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="813f2-116">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="813f2-116">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="813f2-117">Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="813f2-117">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="813f2-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="813f2-118">Text Value</span></span>

<span data-ttu-id="813f2-119">Especifique um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="813f2-119">Specify one of the following values:</span></span>

- <span data-ttu-id="813f2-120">EnumOnly: exibe somente as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="813f2-120">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="813f2-121">CoreOnly: exibe somente as propriedades do objeto de coleção.</span><span class="sxs-lookup"><span data-stu-id="813f2-121">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="813f2-122">Ambos: exibe as propriedades dos objetos na coleção e as propriedades do objeto da coleção.</span><span class="sxs-lookup"><span data-stu-id="813f2-122">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="813f2-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="813f2-123">Remarks</span></span>

<span data-ttu-id="813f2-124">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="813f2-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="813f2-125">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface  **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="813f2-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="813f2-126">O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="813f2-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="813f2-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="813f2-127">See Also</span></span>

[<span data-ttu-id="813f2-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="813f2-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
