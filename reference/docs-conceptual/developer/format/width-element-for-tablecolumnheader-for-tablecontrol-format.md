---
title: Elemento Width para TableColumnHeader para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9540d3d351041ad7cb98a21bb360ebea7eca117
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779906"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="e32b3-102">Elemento Width para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e32b3-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="e32b3-103">Define a largura (em caracteres) de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="e32b3-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="e32b3-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableHeaders elemento para TableControl (Format) TableColumnHeader Element TableHeaders para TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e32b3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e32b3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e32b3-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e32b3-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e32b3-106">Attributes and Elements</span></span>

<span data-ttu-id="e32b3-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Width` elemento usado ao definir cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="e32b3-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="e32b3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e32b3-108">Attributes</span></span>

<span data-ttu-id="e32b3-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e32b3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e32b3-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e32b3-110">Child Elements</span></span>

<span data-ttu-id="e32b3-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e32b3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e32b3-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e32b3-112">Parent Elements</span></span>

|<span data-ttu-id="e32b3-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e32b3-113">Element</span></span>|<span data-ttu-id="e32b3-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e32b3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e32b3-115">Elemento TableColumnHeader para TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e32b3-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="e32b3-116">Define um rótulo, uma largura e um alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="e32b3-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e32b3-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="e32b3-117">Text Value</span></span>

<span data-ttu-id="e32b3-118">Quando possível, especifique uma largura (em caracteres) que seja maior que o comprimento dos valores de propriedade exibidos.</span><span class="sxs-lookup"><span data-stu-id="e32b3-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="e32b3-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="e32b3-119">Remarks</span></span>

<span data-ttu-id="e32b3-120">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="e32b3-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e32b3-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e32b3-121">Example</span></span>

<span data-ttu-id="e32b3-122">O exemplo a seguir mostra um `TableColumnHeader` elemento cuja largura é 16 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e32b3-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="e32b3-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e32b3-123">See Also</span></span>

[<span data-ttu-id="e32b3-124">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="e32b3-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e32b3-125">Elemento TableColumnHeader para TableHeader para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e32b3-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="e32b3-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e32b3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
