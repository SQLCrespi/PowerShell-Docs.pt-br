---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento WideControl (formato)
description: Elemento WideControl (formato)
ms.openlocfilehash: f88e1ce18f87e5e47de473298b3ecf070b71c192
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651266"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="b1c32-103">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b1c32-103">WideControl Element (Format)</span></span>

<span data-ttu-id="b1c32-104">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="b1c32-104">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="b1c32-105">Essa exibição mostra um valor de propriedade única ou um valor de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="b1c32-105">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="b1c32-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b1c32-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1c32-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b1c32-107">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1c32-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b1c32-108">Attributes and Elements</span></span>

<span data-ttu-id="b1c32-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="b1c32-109">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="b1c32-110">Você não pode especificar `AutoSize` os `ColumnNumber` elementos e ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b1c32-110">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1c32-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b1c32-111">Attributes</span></span>

<span data-ttu-id="b1c32-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b1c32-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1c32-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b1c32-113">Child Elements</span></span>

|<span data-ttu-id="b1c32-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1c32-114">Element</span></span>|<span data-ttu-id="b1c32-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1c32-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1c32-116">Elemento AutoSize para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b1c32-116">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="b1c32-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b1c32-117">Optional element.</span></span><br /><br /> <span data-ttu-id="b1c32-118">Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="b1c32-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="b1c32-119">Elemento ColumnNumber para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b1c32-119">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="b1c32-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b1c32-120">Optional element.</span></span><br /><br /> <span data-ttu-id="b1c32-121">Especifica o número de colunas exibidas na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="b1c32-121">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="b1c32-122">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="b1c32-122">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="b1c32-123">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="b1c32-123">Required element.</span></span><br /><br /> <span data-ttu-id="b1c32-124">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="b1c32-124">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b1c32-125">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b1c32-125">Parent Elements</span></span>

|<span data-ttu-id="b1c32-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1c32-126">Element</span></span>|<span data-ttu-id="b1c32-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1c32-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1c32-128">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="b1c32-128">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="b1c32-129">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="b1c32-129">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b1c32-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="b1c32-130">Remarks</span></span>

<span data-ttu-id="b1c32-131">Ao definir uma exibição ampla, você pode adicionar o `AutoSize` elemento ou, `ColumnNumber` mas não pode adicionar ambos.</span><span class="sxs-lookup"><span data-stu-id="b1c32-131">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="b1c32-132">Na maioria dos casos, apenas uma definição é necessária para cada exibição ampla, mas é possível ter várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes.</span><span class="sxs-lookup"><span data-stu-id="b1c32-132">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="b1c32-133">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="b1c32-133">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="b1c32-134">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="b1c32-134">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b1c32-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b1c32-135">Example</span></span>

<span data-ttu-id="b1c32-136">O exemplo a seguir mostra um `WideControl` elemento que é usado para exibir uma propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="b1c32-136">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="b1c32-137">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="b1c32-137">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1c32-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1c32-138">See Also</span></span>

[<span data-ttu-id="b1c32-139">Elemento AutoSize para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b1c32-139">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="b1c32-140">Elemento ColumnNumber para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b1c32-140">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="b1c32-141">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="b1c32-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="b1c32-142">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="b1c32-142">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="b1c32-143">Exibição ampla (Básica)</span><span class="sxs-lookup"><span data-stu-id="b1c32-143">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="b1c32-144">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="b1c32-144">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b1c32-145">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1c32-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
