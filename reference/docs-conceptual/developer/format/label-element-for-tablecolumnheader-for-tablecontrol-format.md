---
title: Elemento de rótulo para TableColumnHeader para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365165"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="b52ed-102">Elemento Label para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b52ed-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="b52ed-103">Define o rótulo que é exibido na parte superior de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="b52ed-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="b52ed-104">Esse elemento é usado ao definir um modo de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="b52ed-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="b52ed-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) rótulo Element para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b52ed-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b52ed-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b52ed-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b52ed-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b52ed-107">Attributes and Elements</span></span>

<span data-ttu-id="b52ed-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Label`.</span><span class="sxs-lookup"><span data-stu-id="b52ed-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="b52ed-109">Apenas um rótulo é permitido para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="b52ed-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="b52ed-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b52ed-110">Attributes</span></span>

<span data-ttu-id="b52ed-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b52ed-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b52ed-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="b52ed-112">Child Elements</span></span>

<span data-ttu-id="b52ed-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b52ed-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b52ed-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="b52ed-114">Parent Elements</span></span>

|<span data-ttu-id="b52ed-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b52ed-115">Element</span></span>|<span data-ttu-id="b52ed-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="b52ed-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b52ed-117">Elemento TableColumnHeader para TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b52ed-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="b52ed-118">Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="b52ed-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b52ed-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="b52ed-119">Text Value</span></span>

<span data-ttu-id="b52ed-120">Especifique o texto que é exibido na parte superior da coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="b52ed-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="b52ed-121">Não há caracteres restritos para o rótulo de coluna.</span><span class="sxs-lookup"><span data-stu-id="b52ed-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="b52ed-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="b52ed-122">Remarks</span></span>

<span data-ttu-id="b52ed-123">Se nenhum rótulo for especificado, o nome da propriedade cujo valor é exibido nas linhas será usado.</span><span class="sxs-lookup"><span data-stu-id="b52ed-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="b52ed-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b52ed-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b52ed-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b52ed-125">Example</span></span>

<span data-ttu-id="b52ed-126">Este exemplo mostra um elemento `TableColumnHeader` cujo rótulo é "coluna 1".</span><span class="sxs-lookup"><span data-stu-id="b52ed-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="b52ed-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b52ed-127">See Also</span></span>

[<span data-ttu-id="b52ed-128">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="b52ed-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b52ed-129">Elemento TableColumnHeader (Format)</span><span class="sxs-lookup"><span data-stu-id="b52ed-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="b52ed-130">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b52ed-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
