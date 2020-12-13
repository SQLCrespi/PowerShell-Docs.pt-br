---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para GroupBy (formato)
description: Elemento PropertyName para GroupBy (formato)
ms.openlocfilehash: 44351c46ff2386f967644fef4f423b3858dc1619
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666137"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="32b29-103">Elemento PropertyName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="32b29-103">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="32b29-104">Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="32b29-104">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="32b29-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) PropertyName para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="32b29-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="32b29-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32b29-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="32b29-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="32b29-107">Attributes and Elements</span></span>

<span data-ttu-id="32b29-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="32b29-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="32b29-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="32b29-109">Attributes</span></span>

<span data-ttu-id="32b29-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="32b29-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="32b29-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="32b29-111">Child Elements</span></span>

<span data-ttu-id="32b29-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="32b29-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="32b29-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="32b29-113">Parent Elements</span></span>

|<span data-ttu-id="32b29-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="32b29-114">Element</span></span>|<span data-ttu-id="32b29-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="32b29-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32b29-116">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="32b29-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="32b29-117">Define como um grupo de objetos .NET é exibido.</span><span class="sxs-lookup"><span data-stu-id="32b29-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="32b29-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="32b29-118">Text Value</span></span>

<span data-ttu-id="32b29-119">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="32b29-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="32b29-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="32b29-120">Remarks</span></span>

<span data-ttu-id="32b29-121">O Windows PowerShell inicia um novo grupo sempre que o valor dessa propriedade é alterado.</span><span class="sxs-lookup"><span data-stu-id="32b29-121">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="32b29-122">Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-groupby-format.md) para iniciar um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="32b29-122">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="32b29-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="32b29-123">Example</span></span>

<span data-ttu-id="32b29-124">O exemplo a seguir mostra como iniciar um novo grupo quando o valor de uma propriedade é alterado.</span><span class="sxs-lookup"><span data-stu-id="32b29-124">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="32b29-125">Para obter um exemplo de um arquivo de formatação completo que inclui esse elemento, consulte [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="32b29-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32b29-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32b29-126">See Also</span></span>

[<span data-ttu-id="32b29-127">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="32b29-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="32b29-128">Elemento ScriptBlock para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="32b29-128">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="32b29-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b29-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
