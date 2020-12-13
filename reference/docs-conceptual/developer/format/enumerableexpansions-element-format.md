---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EnumerableExpansions (formato)
description: Elemento EnumerableExpansions (formato)
ms.openlocfilehash: 789599e6ff368b4685c7937d5b6eb38618752f9e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660180"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="45e5a-103">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="45e5a-103">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="45e5a-104">Define como os objetos de coleção .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="45e5a-104">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="45e5a-105">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format)</span><span class="sxs-lookup"><span data-stu-id="45e5a-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45e5a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45e5a-106">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45e5a-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="45e5a-107">Attributes and Elements</span></span>

<span data-ttu-id="45e5a-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EnumerableExpansions` elemento.</span><span class="sxs-lookup"><span data-stu-id="45e5a-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="45e5a-109">Não há nenhum limite para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="45e5a-109">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="45e5a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="45e5a-110">Attributes</span></span>

<span data-ttu-id="45e5a-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="45e5a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45e5a-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="45e5a-112">Child Elements</span></span>

|<span data-ttu-id="45e5a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="45e5a-113">Element</span></span>|<span data-ttu-id="45e5a-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="45e5a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45e5a-115">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="45e5a-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="45e5a-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="45e5a-116">Optional element.</span></span><br /><br /> <span data-ttu-id="45e5a-117">Define os objetos de coleção .NET específicos que são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="45e5a-117">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="45e5a-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="45e5a-118">Parent Elements</span></span>

|<span data-ttu-id="45e5a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="45e5a-119">Element</span></span>|<span data-ttu-id="45e5a-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="45e5a-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45e5a-121">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="45e5a-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="45e5a-122">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="45e5a-122">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45e5a-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="45e5a-123">Remarks</span></span>

<span data-ttu-id="45e5a-124">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="45e5a-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="45e5a-125">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface  **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="45e5a-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="45e5a-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45e5a-126">See Also</span></span>

[<span data-ttu-id="45e5a-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="45e5a-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
