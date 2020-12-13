---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EnumerableExpansion (formato)
description: Elemento EnumerableExpansion (formato)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668007"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="f52e9-103">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="f52e9-103">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="f52e9-104">Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="f52e9-104">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="f52e9-105">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="f52e9-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f52e9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f52e9-106">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f52e9-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f52e9-107">Attributes and Elements</span></span>

<span data-ttu-id="f52e9-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EnumerableExpansion` elemento.</span><span class="sxs-lookup"><span data-stu-id="f52e9-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f52e9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f52e9-109">Attributes</span></span>

<span data-ttu-id="f52e9-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f52e9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f52e9-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f52e9-111">Child Elements</span></span>

|<span data-ttu-id="f52e9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f52e9-112">Element</span></span>|<span data-ttu-id="f52e9-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f52e9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f52e9-114">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="f52e9-114">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="f52e9-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f52e9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f52e9-116">Define quais objetos de coleção .NET são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="f52e9-116">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="f52e9-117">Elemento Expand (formato)</span><span class="sxs-lookup"><span data-stu-id="f52e9-117">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="f52e9-118">Especifica como o objeto de coleção é expandido para essa definição.</span><span class="sxs-lookup"><span data-stu-id="f52e9-118">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f52e9-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f52e9-119">Parent Elements</span></span>

|<span data-ttu-id="f52e9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f52e9-120">Element</span></span>|<span data-ttu-id="f52e9-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="f52e9-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f52e9-122">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="f52e9-122">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="f52e9-123">Define as diferentes maneiras como os objetos de coleção .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="f52e9-123">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f52e9-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="f52e9-124">Remarks</span></span>

<span data-ttu-id="f52e9-125">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="f52e9-125">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="f52e9-126">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface  **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="f52e9-126">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="f52e9-127">O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="f52e9-127">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="f52e9-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f52e9-128">See Also</span></span>

[<span data-ttu-id="f52e9-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f52e9-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
