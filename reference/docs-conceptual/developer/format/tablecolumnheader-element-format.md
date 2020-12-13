---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableColumnHeader (formato)
description: Elemento TableColumnHeader (formato)
ms.openlocfilehash: 30368512875b7c5c4cf3c686f3d09540dea1bd26
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651525"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="50f82-103">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="50f82-103">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="50f82-104">Define o rótulo, a largura da coluna e o alinhamento do rótulo para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="50f82-104">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="50f82-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="50f82-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="50f82-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="50f82-106">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="50f82-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="50f82-107">Attributes and Elements</span></span>

<span data-ttu-id="50f82-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TableColumnHeader` elemento.</span><span class="sxs-lookup"><span data-stu-id="50f82-108">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="50f82-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="50f82-109">Attributes</span></span>

<span data-ttu-id="50f82-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="50f82-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="50f82-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="50f82-111">Child Elements</span></span>

|<span data-ttu-id="50f82-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="50f82-112">Element</span></span>|<span data-ttu-id="50f82-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="50f82-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50f82-114">Elemento Label para TableColumnHeader para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="50f82-114">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="50f82-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="50f82-115">Optional element.</span></span><br /><br /> <span data-ttu-id="50f82-116">Define o rótulo que é exibido na parte superior da coluna.</span><span class="sxs-lookup"><span data-stu-id="50f82-116">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="50f82-117">Se nenhum rótulo for especificado, o nome da propriedade cujo valor é exibido nas linhas será usado.</span><span class="sxs-lookup"><span data-stu-id="50f82-117">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="50f82-118">Elemento Width para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="50f82-118">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="50f82-119">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="50f82-119">Required element.</span></span><br /><br /> <span data-ttu-id="50f82-120">Especifica a largura (em caracteres) da coluna.</span><span class="sxs-lookup"><span data-stu-id="50f82-120">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="50f82-121">Elemento Alignment para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="50f82-121">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="50f82-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="50f82-122">Optional element.</span></span><br /><br /> <span data-ttu-id="50f82-123">Especifica como o rótulo da coluna é exibido.</span><span class="sxs-lookup"><span data-stu-id="50f82-123">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="50f82-124">Se nenhum alinhamento for especificado, o rótulo será alinhado à esquerda.</span><span class="sxs-lookup"><span data-stu-id="50f82-124">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="50f82-125">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="50f82-125">Parent Elements</span></span>

|<span data-ttu-id="50f82-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="50f82-126">Element</span></span>|<span data-ttu-id="50f82-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="50f82-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50f82-128">Elemento TableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="50f82-128">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="50f82-129">Define as colunas de uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="50f82-129">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="50f82-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="50f82-130">Remarks</span></span>

<span data-ttu-id="50f82-131">Especifique um cabeçalho para cada coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="50f82-131">Specify a header for each column of the table.</span></span> <span data-ttu-id="50f82-132">As colunas são exibidas na ordem em que os `TableColumnHeader` elementos são definidos.</span><span class="sxs-lookup"><span data-stu-id="50f82-132">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="50f82-133">Uma tabela deve ter o mesmo número de `TableColumnHeader` elementos que os `TableRowEntry` elementos.</span><span class="sxs-lookup"><span data-stu-id="50f82-133">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="50f82-134">O cabeçalho da coluna define como o texto na parte superior da tabela é exibido.</span><span class="sxs-lookup"><span data-stu-id="50f82-134">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="50f82-135">As entradas de linha definem quais dados são exibidos nas linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="50f82-135">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="50f82-136">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="50f82-136">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="50f82-137">Exemplo</span><span class="sxs-lookup"><span data-stu-id="50f82-137">Example</span></span>

<span data-ttu-id="50f82-138">O exemplo a seguir mostra dois `TableColumnHeader` elementos.</span><span class="sxs-lookup"><span data-stu-id="50f82-138">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="50f82-139">O primeiro elemento define uma coluna cujo rótulo é "Column 1", tem uma largura de 16 caracteres e cujo rótulo está alinhado à esquerda.</span><span class="sxs-lookup"><span data-stu-id="50f82-139">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="50f82-140">O segundo elemento define uma coluna cujo rótulo é "coluna 2", tem uma largura de 10 caracteres e cujo rótulo é centralizado na coluna.</span><span class="sxs-lookup"><span data-stu-id="50f82-140">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
    <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="50f82-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50f82-141">See Also</span></span>

[<span data-ttu-id="50f82-142">Elemento Alignment para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="50f82-142">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="50f82-143">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="50f82-143">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="50f82-144">Elemento Label para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="50f82-144">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="50f82-145">Elemento TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="50f82-145">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="50f82-146">Largura de TableColumnHeader para o elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="50f82-146">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="50f82-147">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="50f82-147">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
