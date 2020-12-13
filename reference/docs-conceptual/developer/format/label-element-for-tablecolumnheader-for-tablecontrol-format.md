---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Label para TableColumnHeader para TableControl (formato)
description: Elemento Label para TableColumnHeader para TableControl (formato)
ms.openlocfilehash: fe4c209903c04e683b44e2bdcbf381adb6874ace
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667786"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="a0125-103">Elemento Label para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a0125-103">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="a0125-104">Define o rótulo que é exibido na parte superior de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="a0125-104">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="a0125-105">Esse elemento é usado ao definir um modo de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="a0125-105">This element is used when defining a table view.</span></span>

<span data-ttu-id="a0125-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element para TableHeaders para TableControl (Format) rótulo Element para TableColumnHeader para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a0125-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0125-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a0125-107">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0125-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a0125-108">Attributes and Elements</span></span>

<span data-ttu-id="a0125-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento.</span><span class="sxs-lookup"><span data-stu-id="a0125-109">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="a0125-110">Apenas um rótulo é permitido para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="a0125-110">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0125-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0125-111">Attributes</span></span>

<span data-ttu-id="a0125-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a0125-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0125-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a0125-113">Child Elements</span></span>

<span data-ttu-id="a0125-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a0125-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a0125-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a0125-115">Parent Elements</span></span>

|<span data-ttu-id="a0125-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0125-116">Element</span></span>|<span data-ttu-id="a0125-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="a0125-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0125-118">Elemento TableColumnHeader para TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a0125-118">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="a0125-119">Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="a0125-119">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a0125-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="a0125-120">Text Value</span></span>

<span data-ttu-id="a0125-121">Especifique o texto que é exibido na parte superior da coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="a0125-121">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="a0125-122">Não há caracteres restritos para o rótulo de coluna.</span><span class="sxs-lookup"><span data-stu-id="a0125-122">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0125-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="a0125-123">Remarks</span></span>

<span data-ttu-id="a0125-124">Se nenhum rótulo for especificado, o nome da propriedade cujo valor é exibido nas linhas será usado.</span><span class="sxs-lookup"><span data-stu-id="a0125-124">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="a0125-125">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="a0125-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a0125-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a0125-126">Example</span></span>

<span data-ttu-id="a0125-127">Este exemplo mostra um `TableColumnHeader` elemento cujo rótulo é "coluna 1".</span><span class="sxs-lookup"><span data-stu-id="a0125-127">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="a0125-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0125-128">See Also</span></span>

[<span data-ttu-id="a0125-129">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="a0125-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a0125-130">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="a0125-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="a0125-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0125-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
