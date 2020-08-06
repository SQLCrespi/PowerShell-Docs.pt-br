---
title: Elemento Expand (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: deee832254bb8a774ee2c1f5bd451d3ced1bd47a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783646"
---
# <a name="expand-element-format"></a><span data-ttu-id="8f966-102">Elemento Expand (formato)</span><span class="sxs-lookup"><span data-stu-id="8f966-102">Expand Element (Format)</span></span>

<span data-ttu-id="8f966-103">Especifica como o objeto de coleção é expandido para essa definição.</span><span class="sxs-lookup"><span data-stu-id="8f966-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="8f966-104">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion Element (Format) Expand elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="8f966-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8f966-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8f966-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8f966-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8f966-106">Attributes and Elements</span></span>

<span data-ttu-id="8f966-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Expand` elemento.</span><span class="sxs-lookup"><span data-stu-id="8f966-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8f966-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8f966-108">Attributes</span></span>

<span data-ttu-id="8f966-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8f966-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8f966-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="8f966-110">Child Elements</span></span>

<span data-ttu-id="8f966-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8f966-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8f966-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="8f966-112">Parent Elements</span></span>

|<span data-ttu-id="8f966-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f966-113">Element</span></span>|<span data-ttu-id="8f966-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="8f966-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f966-115">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="8f966-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="8f966-116">Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="8f966-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8f966-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="8f966-117">Text Value</span></span>

<span data-ttu-id="8f966-118">Especifique um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="8f966-118">Specify one of the following values:</span></span>

- <span data-ttu-id="8f966-119">EnumOnly: exibe somente as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="8f966-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="8f966-120">CoreOnly: exibe somente as propriedades do objeto de coleção.</span><span class="sxs-lookup"><span data-stu-id="8f966-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="8f966-121">Ambos: exibe as propriedades dos objetos na coleção e as propriedades do objeto da coleção.</span><span class="sxs-lookup"><span data-stu-id="8f966-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f966-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="8f966-122">Remarks</span></span>

<span data-ttu-id="8f966-123">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="8f966-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="8f966-124">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="8f966-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="8f966-125">O comportamento padrão é exibir apenas as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="8f966-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f966-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f966-126">See Also</span></span>

[<span data-ttu-id="8f966-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f966-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
