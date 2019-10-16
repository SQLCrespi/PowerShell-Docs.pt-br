---
title: Elemento WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367985"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="6295b-102">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="6295b-102">WideControl Element (Format)</span></span>

<span data-ttu-id="6295b-103">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="6295b-103">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="6295b-104">Essa exibição mostra um valor de propriedade única ou um valor de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="6295b-104">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="6295b-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6295b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6295b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6295b-106">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6295b-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6295b-107">Attributes and Elements</span></span>

<span data-ttu-id="6295b-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `WideControl`.</span><span class="sxs-lookup"><span data-stu-id="6295b-108">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="6295b-109">Você não pode especificar os elementos `AutoSize` e `ColumnNumber` ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6295b-109">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="6295b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6295b-110">Attributes</span></span>

<span data-ttu-id="6295b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6295b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6295b-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="6295b-112">Child Elements</span></span>

|<span data-ttu-id="6295b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6295b-113">Element</span></span>|<span data-ttu-id="6295b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6295b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6295b-115">Elemento AutoSize para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6295b-115">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="6295b-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6295b-116">Optional element.</span></span><br /><br /> <span data-ttu-id="6295b-117">Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="6295b-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="6295b-118">Elemento ColumnNumber para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6295b-118">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="6295b-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6295b-119">Optional element.</span></span><br /><br /> <span data-ttu-id="6295b-120">Especifica o número de colunas exibidas na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="6295b-120">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="6295b-121">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="6295b-121">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="6295b-122">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="6295b-122">Required element.</span></span><br /><br /> <span data-ttu-id="6295b-123">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="6295b-123">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6295b-124">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="6295b-124">Parent Elements</span></span>

|<span data-ttu-id="6295b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6295b-125">Element</span></span>|<span data-ttu-id="6295b-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="6295b-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6295b-127">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="6295b-127">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="6295b-128">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="6295b-128">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6295b-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="6295b-129">Remarks</span></span>

<span data-ttu-id="6295b-130">Ao definir uma exibição ampla, você pode adicionar o elemento `AutoSize` ou o `ColumnNumber`, mas não pode adicionar ambos.</span><span class="sxs-lookup"><span data-stu-id="6295b-130">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="6295b-131">Na maioria dos casos, apenas uma definição é necessária para cada exibição ampla, mas é possível ter várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes.</span><span class="sxs-lookup"><span data-stu-id="6295b-131">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="6295b-132">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="6295b-132">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="6295b-133">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="6295b-133">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6295b-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6295b-134">Example</span></span>

<span data-ttu-id="6295b-135">O exemplo a seguir mostra um elemento `WideControl` que é usado para exibir uma propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="6295b-135">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

<span data-ttu-id="6295b-136">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="6295b-136">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6295b-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6295b-137">See Also</span></span>

[<span data-ttu-id="6295b-138">Elemento AutoSize para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6295b-138">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="6295b-139">Elemento ColumnNumber para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6295b-139">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="6295b-140">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="6295b-140">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="6295b-141">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="6295b-141">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="6295b-142">Exibição ampla (básica)</span><span class="sxs-lookup"><span data-stu-id="6295b-142">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="6295b-143">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="6295b-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="6295b-144">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6295b-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
