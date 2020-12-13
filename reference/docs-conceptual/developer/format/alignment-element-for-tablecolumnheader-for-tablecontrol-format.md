---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Alignment para TableColumnHeader para TableControl (formato)
description: Elemento Alignment para TableColumnHeader para TableControl (formato)
ms.openlocfilehash: cf8b90c12c28951283b5870186e2c88d427318a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666817"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="dd09c-103">Elemento Alignment para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dd09c-103">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="dd09c-104">Define como os dados em um cabeçalho de coluna são exibidos.</span><span class="sxs-lookup"><span data-stu-id="dd09c-104">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="dd09c-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) TableControl Element (Format) TableHeaders elemento (Format) TableColumnHeader elemento (Format) o elemento de alinhamento para TableColumnHeader (Format)</span><span class="sxs-lookup"><span data-stu-id="dd09c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dd09c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd09c-106">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dd09c-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="dd09c-107">Attributes and Elements</span></span>

<span data-ttu-id="dd09c-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Alignment` elemento.</span><span class="sxs-lookup"><span data-stu-id="dd09c-108">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dd09c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="dd09c-109">Attributes</span></span>

<span data-ttu-id="dd09c-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="dd09c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dd09c-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="dd09c-111">Child Elements</span></span>

<span data-ttu-id="dd09c-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="dd09c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dd09c-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="dd09c-113">Parent Elements</span></span>

|<span data-ttu-id="dd09c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd09c-114">Element</span></span>|<span data-ttu-id="dd09c-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd09c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dd09c-116">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="dd09c-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="dd09c-117">Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="dd09c-117">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dd09c-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="dd09c-118">Text Value</span></span>

<span data-ttu-id="dd09c-119">Especifique um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd09c-119">Specify one of the following values.</span></span> <span data-ttu-id="dd09c-120">Esses valores não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dd09c-120">These values are not case-sensitive.</span></span>

<span data-ttu-id="dd09c-121">À esquerda alinha os dados exibidos na coluna à esquerda, esse será o padrão se esse elemento não for especificado.</span><span class="sxs-lookup"><span data-stu-id="dd09c-121">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="dd09c-122">Alinha à direita os dados exibidos na coluna à direita.</span><span class="sxs-lookup"><span data-stu-id="dd09c-122">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="dd09c-123">Centraliza os dados exibidos na coluna.</span><span class="sxs-lookup"><span data-stu-id="dd09c-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd09c-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd09c-124">Remarks</span></span>

<span data-ttu-id="dd09c-125">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="dd09c-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="dd09c-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dd09c-126">Example</span></span>

<span data-ttu-id="dd09c-127">Este exemplo mostra um `TableColumnHeader` elemento cujos dados estão alinhados à esquerda.</span><span class="sxs-lookup"><span data-stu-id="dd09c-127">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="dd09c-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd09c-128">See Also</span></span>

[<span data-ttu-id="dd09c-129">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="dd09c-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="dd09c-130">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="dd09c-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="dd09c-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd09c-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
