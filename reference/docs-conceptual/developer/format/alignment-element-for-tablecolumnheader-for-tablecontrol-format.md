---
title: Elemento Alignment para TableColumnHeader para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1bf395b84af90d725c14b2f0ef569f72b5fcc613
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783918"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="93813-102">Elemento Alignment para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="93813-102">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="93813-103">Define como os dados em um cabeçalho de coluna são exibidos.</span><span class="sxs-lookup"><span data-stu-id="93813-103">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="93813-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) TableControl Element (Format) TableHeaders elemento (Format) TableColumnHeader elemento (Format) o elemento de alinhamento para TableColumnHeader (Format)</span><span class="sxs-lookup"><span data-stu-id="93813-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93813-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="93813-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93813-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="93813-106">Attributes and Elements</span></span>

<span data-ttu-id="93813-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Alignment` elemento.</span><span class="sxs-lookup"><span data-stu-id="93813-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="93813-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="93813-108">Attributes</span></span>

<span data-ttu-id="93813-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="93813-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93813-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="93813-110">Child Elements</span></span>

<span data-ttu-id="93813-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="93813-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93813-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="93813-112">Parent Elements</span></span>

|<span data-ttu-id="93813-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="93813-113">Element</span></span>|<span data-ttu-id="93813-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="93813-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93813-115">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="93813-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="93813-116">Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="93813-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="93813-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="93813-117">Text Value</span></span>

<span data-ttu-id="93813-118">Especifique um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="93813-118">Specify one of the following values.</span></span> <span data-ttu-id="93813-119">Esses valores não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="93813-119">These values are not case-sensitive.</span></span>

<span data-ttu-id="93813-120">À esquerda alinha os dados exibidos na coluna à esquerda, esse será o padrão se esse elemento não for especificado.</span><span class="sxs-lookup"><span data-stu-id="93813-120">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="93813-121">Alinha à direita os dados exibidos na coluna à direita.</span><span class="sxs-lookup"><span data-stu-id="93813-121">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="93813-122">Centraliza os dados exibidos na coluna.</span><span class="sxs-lookup"><span data-stu-id="93813-122">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="93813-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="93813-123">Remarks</span></span>

<span data-ttu-id="93813-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="93813-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="93813-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="93813-125">Example</span></span>

<span data-ttu-id="93813-126">Este exemplo mostra um `TableColumnHeader` elemento cujos dados estão alinhados à esquerda.</span><span class="sxs-lookup"><span data-stu-id="93813-126">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="93813-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93813-127">See Also</span></span>

[<span data-ttu-id="93813-128">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="93813-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="93813-129">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="93813-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="93813-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="93813-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
