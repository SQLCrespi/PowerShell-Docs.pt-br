---
title: Elemento EnumerableExpansion (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 81a8959c19502a2e56f4cfa48a1e480509d84b6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774041"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="26491-102">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="26491-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="26491-103">Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="26491-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="26491-104">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="26491-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="26491-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="26491-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="26491-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="26491-106">Attributes and Elements</span></span>

<span data-ttu-id="26491-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EnumerableExpansion` elemento.</span><span class="sxs-lookup"><span data-stu-id="26491-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="26491-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="26491-108">Attributes</span></span>

<span data-ttu-id="26491-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="26491-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="26491-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="26491-110">Child Elements</span></span>

|<span data-ttu-id="26491-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="26491-111">Element</span></span>|<span data-ttu-id="26491-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="26491-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26491-113">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="26491-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="26491-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="26491-114">Optional element.</span></span><br /><br /> <span data-ttu-id="26491-115">Define quais objetos de coleção .NET são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="26491-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="26491-116">Elemento Expand (formato)</span><span class="sxs-lookup"><span data-stu-id="26491-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="26491-117">Especifica como o objeto de coleção é expandido para essa definição.</span><span class="sxs-lookup"><span data-stu-id="26491-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="26491-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="26491-118">Parent Elements</span></span>

|<span data-ttu-id="26491-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="26491-119">Element</span></span>|<span data-ttu-id="26491-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="26491-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26491-121">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="26491-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="26491-122">Define as diferentes maneiras como os objetos de coleção .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="26491-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="26491-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="26491-123">Remarks</span></span>

<span data-ttu-id="26491-124">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="26491-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="26491-125">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="26491-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="26491-126">O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="26491-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="26491-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26491-127">See Also</span></span>

[<span data-ttu-id="26491-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="26491-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
