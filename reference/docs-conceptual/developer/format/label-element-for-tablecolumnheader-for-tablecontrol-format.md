---
title: Elemento de rótulo para TableColumnHeader para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b7b1d6825d3bca0e36b230415d19c2ac48377a46
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785737"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="f4b64-102">Elemento Label para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f4b64-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="f4b64-103">Define o rótulo que é exibido na parte superior de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="f4b64-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="f4b64-104">Esse elemento é usado ao definir um modo de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="f4b64-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="f4b64-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element para TableHeaders para TableControl (Format) rótulo Element para TableColumnHeader para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f4b64-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4b64-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f4b64-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4b64-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f4b64-107">Attributes and Elements</span></span>

<span data-ttu-id="f4b64-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento.</span><span class="sxs-lookup"><span data-stu-id="f4b64-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="f4b64-109">Apenas um rótulo é permitido para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="f4b64-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4b64-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f4b64-110">Attributes</span></span>

<span data-ttu-id="f4b64-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f4b64-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4b64-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f4b64-112">Child Elements</span></span>

<span data-ttu-id="f4b64-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f4b64-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4b64-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f4b64-114">Parent Elements</span></span>

|<span data-ttu-id="f4b64-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f4b64-115">Element</span></span>|<span data-ttu-id="f4b64-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4b64-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4b64-117">Elemento TableColumnHeader para TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f4b64-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="f4b64-118">Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="f4b64-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f4b64-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f4b64-119">Text Value</span></span>

<span data-ttu-id="f4b64-120">Especifique o texto que é exibido na parte superior da coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="f4b64-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="f4b64-121">Não há caracteres restritos para o rótulo de coluna.</span><span class="sxs-lookup"><span data-stu-id="f4b64-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4b64-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="f4b64-122">Remarks</span></span>

<span data-ttu-id="f4b64-123">Se nenhum rótulo for especificado, o nome da propriedade cujo valor é exibido nas linhas será usado.</span><span class="sxs-lookup"><span data-stu-id="f4b64-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="f4b64-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f4b64-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f4b64-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f4b64-125">Example</span></span>

<span data-ttu-id="f4b64-126">Este exemplo mostra um `TableColumnHeader` elemento cujo rótulo é "coluna 1".</span><span class="sxs-lookup"><span data-stu-id="f4b64-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="f4b64-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4b64-127">See Also</span></span>

[<span data-ttu-id="f4b64-128">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="f4b64-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f4b64-129">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="f4b64-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="f4b64-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4b64-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
