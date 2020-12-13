---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableColumnItem para TableColumnItems para TableControl (formato)
description: Elemento TableColumnItem para TableColumnItems para TableControl (formato)
ms.openlocfilehash: 8ef5158c9bb9f074d5c58190d4d3b20c10c83744
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659861"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="bfed6-103">Elemento TableColumnItem para TableColumnItems para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-103">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="bfed6-104">Define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="bfed6-104">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="bfed6-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element para TableRowEntries para TableControl (Format) TableColumnItems Element para TableControlEntry para TableControl (Format) TableColumnItem Element para TableColumnItems para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="bfed6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bfed6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bfed6-106">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bfed6-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bfed6-107">Attributes and Elements</span></span>

<span data-ttu-id="bfed6-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TableColumnItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="bfed6-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bfed6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="bfed6-109">Attributes</span></span>

<span data-ttu-id="bfed6-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bfed6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bfed6-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bfed6-111">Child Elements</span></span>

|<span data-ttu-id="bfed6-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfed6-112">Element</span></span>|<span data-ttu-id="bfed6-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="bfed6-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bfed6-114">Elemento Alignment para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-114">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="bfed6-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bfed6-115">Optional element.</span></span><br /><br /> <span data-ttu-id="bfed6-116">Define como os dados em uma coluna da linha são exibidos.</span><span class="sxs-lookup"><span data-stu-id="bfed6-116">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="bfed6-117">Elemento FormatString para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-117">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="bfed6-118">Especifica um padrão de formato que é usado para formatar os dados na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="bfed6-118">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="bfed6-119">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-119">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="bfed6-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bfed6-120">Optional element.</span></span><br /><br /> <span data-ttu-id="bfed6-121">Especifica o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="bfed6-121">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="bfed6-122">Elemento ScriptBlock para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-122">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="bfed6-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bfed6-123">Optional element.</span></span><br /><br /> <span data-ttu-id="bfed6-124">Especifica o script cujo valor é exibido na coluna de uma linha.</span><span class="sxs-lookup"><span data-stu-id="bfed6-124">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bfed6-125">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bfed6-125">Parent Elements</span></span>

|<span data-ttu-id="bfed6-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfed6-126">Element</span></span>|<span data-ttu-id="bfed6-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="bfed6-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bfed6-128">Elemento TableColumnItems para TableControlEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="bfed6-128">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="bfed6-129">Define as propriedades ou os scripts cujos valores são exibidos na linha.</span><span class="sxs-lookup"><span data-stu-id="bfed6-129">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bfed6-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="bfed6-130">Remarks</span></span>

<span data-ttu-id="bfed6-131">Você pode especificar uma propriedade de um objeto ou um script em cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="bfed6-131">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="bfed6-132">Se nenhum elemento filho for especificado, o item será um espaço reservado e nenhum dado será exibido.</span><span class="sxs-lookup"><span data-stu-id="bfed6-132">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="bfed6-133">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="bfed6-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="bfed6-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bfed6-134">Example</span></span>

<span data-ttu-id="bfed6-135">Este exemplo mostra um `TableColumnItem` elemento que exibe o valor da `Status` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="bfed6-135">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="bfed6-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bfed6-136">See Also</span></span>

[<span data-ttu-id="bfed6-137">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="bfed6-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="bfed6-138">Elemento Alignment para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-138">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="bfed6-139">Elemento TableColumnItems (Format)</span><span class="sxs-lookup"><span data-stu-id="bfed6-139">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="bfed6-140">Elemento FormatString para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-140">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="bfed6-141">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-141">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="bfed6-142">Elemento ScriptBlock para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfed6-142">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="bfed6-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfed6-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
