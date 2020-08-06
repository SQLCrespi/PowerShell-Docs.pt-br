---
title: Elemento EnumerableExpansions (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2b536b1ab9b34b0089d0a38d3c5dc7a937176443
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774007"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="782e6-102">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="782e6-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="782e6-103">Define como os objetos de coleção .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="782e6-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="782e6-104">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format)</span><span class="sxs-lookup"><span data-stu-id="782e6-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="782e6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="782e6-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="782e6-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="782e6-106">Attributes and Elements</span></span>

<span data-ttu-id="782e6-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EnumerableExpansions` elemento.</span><span class="sxs-lookup"><span data-stu-id="782e6-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="782e6-108">Não há nenhum limite para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="782e6-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="782e6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="782e6-109">Attributes</span></span>

<span data-ttu-id="782e6-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="782e6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="782e6-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="782e6-111">Child Elements</span></span>

|<span data-ttu-id="782e6-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="782e6-112">Element</span></span>|<span data-ttu-id="782e6-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="782e6-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="782e6-114">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="782e6-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="782e6-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="782e6-115">Optional element.</span></span><br /><br /> <span data-ttu-id="782e6-116">Define os objetos de coleção .NET específicos que são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="782e6-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="782e6-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="782e6-117">Parent Elements</span></span>

|<span data-ttu-id="782e6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="782e6-118">Element</span></span>|<span data-ttu-id="782e6-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="782e6-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="782e6-120">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="782e6-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="782e6-121">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="782e6-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="782e6-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="782e6-122">Remarks</span></span>

<span data-ttu-id="782e6-123">Esse elemento é usado para definir como os objetos de coleção e os objetos na coleção são exibidos.</span><span class="sxs-lookup"><span data-stu-id="782e6-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="782e6-124">Nesse caso, um objeto de coleção refere-se a qualquer objeto que ofereça suporte à interface **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="782e6-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="782e6-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="782e6-125">See Also</span></span>

[<span data-ttu-id="782e6-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="782e6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
