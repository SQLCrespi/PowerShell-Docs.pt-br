---
title: Elemento TableHeaders (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361815"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="2d520-102">Elemento TableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="2d520-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="2d520-103">Define os cabeçalhos para as colunas de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2d520-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="2d520-104">Elemento ViewDefinitions (Format) View element (Format) o elemento TableControl (Format) elemento TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2d520-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2d520-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2d520-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2d520-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2d520-106">Attributes and Elements</span></span>

<span data-ttu-id="2d520-107">As seções a seguir descrevem os atributos, os elementos filho e os elementos pai do elemento `TableHeaders`.</span><span class="sxs-lookup"><span data-stu-id="2d520-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="2d520-108">Deve haver um elemento filho para cada propriedade do objeto a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="2d520-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="2d520-109">As informações de cabeçalho de coluna são exibidas na ordem em que os elementos filho são especificados.</span><span class="sxs-lookup"><span data-stu-id="2d520-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="2d520-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d520-110">Attributes</span></span>

<span data-ttu-id="2d520-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2d520-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2d520-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="2d520-112">Child Elements</span></span>

|<span data-ttu-id="2d520-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d520-113">Element</span></span>|<span data-ttu-id="2d520-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="2d520-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2d520-115">Elemento TableColumnHeader (Format)</span><span class="sxs-lookup"><span data-stu-id="2d520-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="2d520-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2d520-116">Optional element.</span></span><br /><br /> <span data-ttu-id="2d520-117">Define o rótulo, a largura e o alinhamento dos dados para uma coluna de uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="2d520-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2d520-118">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="2d520-118">Parent Elements</span></span>

|<span data-ttu-id="2d520-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d520-119">Element</span></span>|<span data-ttu-id="2d520-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="2d520-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2d520-121">Elemento TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2d520-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="2d520-122">Define um formato de tabela para uma exibição.</span><span class="sxs-lookup"><span data-stu-id="2d520-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2d520-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="2d520-123">Remarks</span></span>

<span data-ttu-id="2d520-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="2d520-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2d520-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2d520-125">Example</span></span>

<span data-ttu-id="2d520-126">Este exemplo mostra um elemento `TableHeaders` que define dois cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="2d520-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2d520-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d520-127">See Also</span></span>

[<span data-ttu-id="2d520-128">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="2d520-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2d520-129">Elemento TableColumnHeader (Format)</span><span class="sxs-lookup"><span data-stu-id="2d520-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="2d520-130">Elemento TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2d520-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="2d520-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d520-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
