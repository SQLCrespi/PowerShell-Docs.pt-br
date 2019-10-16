---
title: Elemento EnumerableExpansion (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368745"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="b6fe2-102">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="b6fe2-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="b6fe2-103">Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="b6fe2-104">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="b6fe2-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b6fe2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b6fe2-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6fe2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b6fe2-106">Attributes and Elements</span></span>

<span data-ttu-id="b6fe2-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `EnumerableExpansion`.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6fe2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b6fe2-108">Attributes</span></span>

<span data-ttu-id="b6fe2-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6fe2-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="b6fe2-110">Child Elements</span></span>

|<span data-ttu-id="b6fe2-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6fe2-111">Element</span></span>|<span data-ttu-id="b6fe2-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6fe2-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6fe2-113">Elemento EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="b6fe2-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="b6fe2-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-114">Optional element.</span></span><br /><br /> <span data-ttu-id="b6fe2-115">Define quais objetos de coleção .NET são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="b6fe2-116">Elemento Expand (formato)</span><span class="sxs-lookup"><span data-stu-id="b6fe2-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="b6fe2-117">Especifica como o objeto de coleção é expandido para essa definição.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b6fe2-118">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="b6fe2-118">Parent Elements</span></span>

|<span data-ttu-id="b6fe2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6fe2-119">Element</span></span>|<span data-ttu-id="b6fe2-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6fe2-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6fe2-121">Elemento EnumerableExpansions (Format)</span><span class="sxs-lookup"><span data-stu-id="b6fe2-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="b6fe2-122">Define as diferentes maneiras como os objetos de coleção .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b6fe2-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="b6fe2-123">Remarks</span></span>

<span data-ttu-id="b6fe2-124">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="b6fe2-125">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="b6fe2-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="b6fe2-126">O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="b6fe2-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6fe2-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6fe2-127">See Also</span></span>

[<span data-ttu-id="b6fe2-128">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6fe2-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
