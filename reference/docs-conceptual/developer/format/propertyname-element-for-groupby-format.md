---
title: Elemento PropertyName para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362515"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="9dc02-102">Elemento PropertyName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9dc02-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="9dc02-103">Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="9dc02-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="9dc02-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) PropertyName para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9dc02-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9dc02-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9dc02-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9dc02-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9dc02-106">Attributes and Elements</span></span>

<span data-ttu-id="9dc02-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="9dc02-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9dc02-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9dc02-108">Attributes</span></span>

<span data-ttu-id="9dc02-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9dc02-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9dc02-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="9dc02-110">Child Elements</span></span>

<span data-ttu-id="9dc02-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9dc02-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9dc02-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="9dc02-112">Parent Elements</span></span>

|<span data-ttu-id="9dc02-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9dc02-113">Element</span></span>|<span data-ttu-id="9dc02-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="9dc02-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9dc02-115">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9dc02-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="9dc02-116">Define como um grupo de objetos .NET é exibido.</span><span class="sxs-lookup"><span data-stu-id="9dc02-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9dc02-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9dc02-117">Text Value</span></span>

<span data-ttu-id="9dc02-118">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="9dc02-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9dc02-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="9dc02-119">Remarks</span></span>

<span data-ttu-id="9dc02-120">O Windows PowerShell inicia um novo grupo sempre que o valor dessa propriedade é alterado.</span><span class="sxs-lookup"><span data-stu-id="9dc02-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="9dc02-121">Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-groupby-format.md) para iniciar um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="9dc02-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="9dc02-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9dc02-122">Example</span></span>

<span data-ttu-id="9dc02-123">O exemplo a seguir mostra como iniciar um novo grupo quando o valor de uma propriedade é alterado.</span><span class="sxs-lookup"><span data-stu-id="9dc02-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="9dc02-124">Para obter um exemplo de um arquivo de formatação completo que inclui esse elemento, consulte [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="9dc02-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9dc02-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9dc02-125">See Also</span></span>

[<span data-ttu-id="9dc02-126">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9dc02-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="9dc02-127">Elemento ScriptBlock para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9dc02-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="9dc02-128">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dc02-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
