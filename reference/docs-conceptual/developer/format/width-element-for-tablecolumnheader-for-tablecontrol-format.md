---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Width para TableColumnHeader para TableControl (formato)
description: Elemento Width para TableColumnHeader para TableControl (formato)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658251"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="d8187-103">Elemento Width para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="d8187-103">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="d8187-104">Define a largura (em caracteres) de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="d8187-104">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="d8187-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element TableHeaders para TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d8187-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d8187-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d8187-106">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d8187-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d8187-107">Attributes and Elements</span></span>

<span data-ttu-id="d8187-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Width` elemento usado ao definir cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="d8187-108">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="d8187-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d8187-109">Attributes</span></span>

<span data-ttu-id="d8187-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d8187-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d8187-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d8187-111">Child Elements</span></span>

<span data-ttu-id="d8187-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d8187-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d8187-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d8187-113">Parent Elements</span></span>

|<span data-ttu-id="d8187-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8187-114">Element</span></span>|<span data-ttu-id="d8187-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="d8187-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d8187-116">Elemento TableColumnHeader para TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d8187-116">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="d8187-117">Define um rótulo, uma largura e um alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="d8187-117">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d8187-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="d8187-118">Text Value</span></span>

<span data-ttu-id="d8187-119">Quando possível, especifique uma largura (em caracteres) que seja maior que o comprimento dos valores de propriedade exibidos.</span><span class="sxs-lookup"><span data-stu-id="d8187-119">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8187-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="d8187-120">Remarks</span></span>

<span data-ttu-id="d8187-121">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d8187-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d8187-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d8187-122">Example</span></span>

<span data-ttu-id="d8187-123">O exemplo a seguir mostra um `TableColumnHeader` elemento cuja largura é 16 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d8187-123">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="d8187-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8187-124">See Also</span></span>

[<span data-ttu-id="d8187-125">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="d8187-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d8187-126">Elemento TableColumnHeader para TableHeader para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d8187-126">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="d8187-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8187-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
