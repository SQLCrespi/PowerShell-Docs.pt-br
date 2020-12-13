---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableColumnItems para TableRowEntry para TableControl (formato)
description: Elemento TableColumnItems para TableRowEntry para TableControl (formato)
ms.openlocfilehash: 4d600a366d2be1c453f05b301bdf575351dd51c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667752"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="29b38-103">Elemento TableColumnItems para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="29b38-103">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="29b38-104">Define as propriedades ou os scripts cujos valores são exibidos em uma linha.</span><span class="sxs-lookup"><span data-stu-id="29b38-104">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="29b38-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element para TableRowEntries para TableControl (Format) TableColumnItems Element para TableControlEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="29b38-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="29b38-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="29b38-106">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="29b38-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="29b38-107">Attributes and Elements</span></span>

<span data-ttu-id="29b38-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TableColumnItems` elemento.</span><span class="sxs-lookup"><span data-stu-id="29b38-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="29b38-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="29b38-109">Attributes</span></span>

<span data-ttu-id="29b38-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="29b38-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="29b38-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="29b38-111">Child Elements</span></span>

|<span data-ttu-id="29b38-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="29b38-112">Element</span></span>|<span data-ttu-id="29b38-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="29b38-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="29b38-114">Elemento TableColumnItem para TableColumnItems para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="29b38-114">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="29b38-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="29b38-115">Required element.</span></span><br /><br /> <span data-ttu-id="29b38-116">Define a propriedade ou o script cujo valor é exibido em uma coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="29b38-116">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="29b38-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="29b38-117">Parent Elements</span></span>

|<span data-ttu-id="29b38-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="29b38-118">Element</span></span>|<span data-ttu-id="29b38-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="29b38-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="29b38-120">Elemento TableRowEntry para TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="29b38-120">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="29b38-121">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="29b38-121">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="29b38-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="29b38-122">Remarks</span></span>

<span data-ttu-id="29b38-123">Um `TableColumnItem` elemento é necessário para cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="29b38-123">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="29b38-124">A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="29b38-124">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="29b38-125">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="29b38-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="29b38-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="29b38-126">Example</span></span>

<span data-ttu-id="29b38-127">O exemplo a seguir mostra um `TableColumnItems` elemento que define três propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="29b38-127">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="29b38-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29b38-128">See Also</span></span>

[<span data-ttu-id="29b38-129">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="29b38-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="29b38-130">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="29b38-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="29b38-131">Elemento TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="29b38-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="29b38-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="29b38-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
