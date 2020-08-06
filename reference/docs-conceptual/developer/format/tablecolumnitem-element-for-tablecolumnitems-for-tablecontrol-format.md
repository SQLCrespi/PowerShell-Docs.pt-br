---
title: Elemento TableColumnItem para TableColumnItems para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: beadf771f02519394d799a03db374050e3302321
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785159"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="387ed-102">Elemento TableColumnItem para TableColumnItems para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="387ed-103">Define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="387ed-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="387ed-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element para TableRowEntries para TableControl (Format) TableColumnItems Element para TableControlEntry para TableControl (Format) TableColumnItem Element para TableColumnItems para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="387ed-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="387ed-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="387ed-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="387ed-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="387ed-106">Attributes and Elements</span></span>

<span data-ttu-id="387ed-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TableColumnItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="387ed-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="387ed-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="387ed-108">Attributes</span></span>

<span data-ttu-id="387ed-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="387ed-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="387ed-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="387ed-110">Child Elements</span></span>

|<span data-ttu-id="387ed-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="387ed-111">Element</span></span>|<span data-ttu-id="387ed-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="387ed-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="387ed-113">Elemento Alignment para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="387ed-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="387ed-114">Optional element.</span></span><br /><br /> <span data-ttu-id="387ed-115">Define como os dados em uma coluna da linha são exibidos.</span><span class="sxs-lookup"><span data-stu-id="387ed-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="387ed-116">Elemento FormatString para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="387ed-117">Especifica um padrão de formato que é usado para formatar os dados na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="387ed-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="387ed-118">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="387ed-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="387ed-119">Optional element.</span></span><br /><br /> <span data-ttu-id="387ed-120">Especifica o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="387ed-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="387ed-121">Elemento ScriptBlock para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="387ed-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="387ed-122">Optional element.</span></span><br /><br /> <span data-ttu-id="387ed-123">Especifica o script cujo valor é exibido na coluna de uma linha.</span><span class="sxs-lookup"><span data-stu-id="387ed-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="387ed-124">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="387ed-124">Parent Elements</span></span>

|<span data-ttu-id="387ed-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="387ed-125">Element</span></span>|<span data-ttu-id="387ed-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="387ed-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="387ed-127">Elemento TableColumnItems para TableControlEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="387ed-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="387ed-128">Define as propriedades ou os scripts cujos valores são exibidos na linha.</span><span class="sxs-lookup"><span data-stu-id="387ed-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="387ed-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="387ed-129">Remarks</span></span>

<span data-ttu-id="387ed-130">Você pode especificar uma propriedade de um objeto ou um script em cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="387ed-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="387ed-131">Se nenhum elemento filho for especificado, o item será um espaço reservado e nenhum dado será exibido.</span><span class="sxs-lookup"><span data-stu-id="387ed-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="387ed-132">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="387ed-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="387ed-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="387ed-133">Example</span></span>

<span data-ttu-id="387ed-134">Este exemplo mostra um `TableColumnItem` elemento que exibe o valor da `Status` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="387ed-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="387ed-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="387ed-135">See Also</span></span>

[<span data-ttu-id="387ed-136">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="387ed-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="387ed-137">Elemento Alignment para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="387ed-138">Elemento TableColumnItems (Format)</span><span class="sxs-lookup"><span data-stu-id="387ed-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="387ed-139">Elemento FormatString para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="387ed-140">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="387ed-141">Elemento ScriptBlock para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="387ed-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="387ed-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="387ed-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
