---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableRowEntry para TableRowEntries para TableControl (formato)
description: Elemento TableRowEntry para TableRowEntries para TableControl (formato)
ms.openlocfilehash: 60d64b7c14b40e87825ada36e19f52a66fe8b6cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659770"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a><span data-ttu-id="39df9-103">Elemento TableRowEntry para TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="39df9-103">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

<span data-ttu-id="39df9-104">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="39df9-104">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="39df9-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="39df9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="39df9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="39df9-106">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="39df9-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="39df9-107">Attributes and Elements</span></span>

<span data-ttu-id="39df9-108">As seções a seguir descrevem atributos, elementos filho e elemento pai do `TableRowEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="39df9-108">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="39df9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="39df9-109">Attributes</span></span>

<span data-ttu-id="39df9-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="39df9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="39df9-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="39df9-111">Child Elements</span></span>

|<span data-ttu-id="39df9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="39df9-112">Element</span></span>|<span data-ttu-id="39df9-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="39df9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="39df9-114">Elemento EntrySelectedBy para TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="39df9-114">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="39df9-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="39df9-115">Required element.</span></span><br /><br /> <span data-ttu-id="39df9-116">Define os objetos cujos valores de propriedade são exibidos na linha.</span><span class="sxs-lookup"><span data-stu-id="39df9-116">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="39df9-117">Elemento TableColumnItems para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="39df9-117">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="39df9-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="39df9-118">Required element.</span></span><br /><br /> <span data-ttu-id="39df9-119">Define as propriedades ou os scripts cujos valores são exibidos.</span><span class="sxs-lookup"><span data-stu-id="39df9-119">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="39df9-120">Elemento Wrap para TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="39df9-120">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="39df9-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="39df9-121">Optional element.</span></span><br /><br /> <span data-ttu-id="39df9-122">Especifica que o texto que excede a largura da coluna é exibido na próxima linha.</span><span class="sxs-lookup"><span data-stu-id="39df9-122">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="39df9-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="39df9-123">Parent Elements</span></span>

|<span data-ttu-id="39df9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="39df9-124">Element</span></span>|<span data-ttu-id="39df9-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="39df9-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="39df9-126">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="39df9-126">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="39df9-127">Define as linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="39df9-127">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="39df9-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="39df9-128">Remarks</span></span>

<span data-ttu-id="39df9-129">Um `TableColumnItems` elemento e um `EntrySelectedBy` elemento devem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="39df9-129">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="39df9-130">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="39df9-130">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="39df9-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="39df9-131">Example</span></span>

<span data-ttu-id="39df9-132">O exemplo a seguir mostra um `TableRowEntry` elemento que define uma linha que exibe os valores de duas propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="39df9-132">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="39df9-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39df9-133">See Also</span></span>

[<span data-ttu-id="39df9-134">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="39df9-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="39df9-135">Elemento EntrySelectedBy para TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="39df9-135">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="39df9-136">Elemento TableColumnItems para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="39df9-136">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="39df9-137">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="39df9-137">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="39df9-138">Elemento Wrap para TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="39df9-138">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="39df9-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="39df9-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
