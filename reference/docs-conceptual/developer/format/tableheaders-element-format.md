---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableHeaders (formato)
description: Elemento TableHeaders (formato)
ms.openlocfilehash: 5ac4dccae746c167ebf95add9f3d18030a2b3a99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659826"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="351dc-103">Elemento TableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="351dc-103">TableHeaders Element (Format)</span></span>

<span data-ttu-id="351dc-104">Define os cabeçalhos para as colunas de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="351dc-104">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="351dc-105">Elemento ViewDefinitions (Format) View element (Format) o elemento TableControl (Format) elemento TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="351dc-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="351dc-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="351dc-106">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="351dc-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="351dc-107">Attributes and Elements</span></span>

<span data-ttu-id="351dc-108">As seções a seguir descrevem os atributos, os elementos filho e os elementos pai do `TableHeaders` elemento.</span><span class="sxs-lookup"><span data-stu-id="351dc-108">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="351dc-109">Deve haver um elemento filho para cada propriedade do objeto a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="351dc-109">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="351dc-110">As informações de cabeçalho de coluna são exibidas na ordem em que os elementos filho são especificados.</span><span class="sxs-lookup"><span data-stu-id="351dc-110">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="351dc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="351dc-111">Attributes</span></span>

<span data-ttu-id="351dc-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="351dc-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="351dc-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="351dc-113">Child Elements</span></span>

|<span data-ttu-id="351dc-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="351dc-114">Element</span></span>|<span data-ttu-id="351dc-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="351dc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="351dc-116">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="351dc-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="351dc-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="351dc-117">Optional element.</span></span><br /><br /> <span data-ttu-id="351dc-118">Define o rótulo, a largura e o alinhamento dos dados para uma coluna de uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="351dc-118">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="351dc-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="351dc-119">Parent Elements</span></span>

|<span data-ttu-id="351dc-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="351dc-120">Element</span></span>|<span data-ttu-id="351dc-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="351dc-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="351dc-122">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="351dc-122">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="351dc-123">Define um formato de tabela para uma exibição.</span><span class="sxs-lookup"><span data-stu-id="351dc-123">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="351dc-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="351dc-124">Remarks</span></span>

<span data-ttu-id="351dc-125">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="351dc-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="351dc-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="351dc-126">Example</span></span>

<span data-ttu-id="351dc-127">Este exemplo mostra um `TableHeaders` elemento que define dois cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="351dc-127">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="351dc-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="351dc-128">See Also</span></span>

[<span data-ttu-id="351dc-129">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="351dc-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="351dc-130">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="351dc-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="351dc-131">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="351dc-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="351dc-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="351dc-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
