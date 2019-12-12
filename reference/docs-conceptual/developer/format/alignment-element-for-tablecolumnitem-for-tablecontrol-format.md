---
title: Elemento Alignment para TableColumnItem para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b07a53df-64f1-49b0-8cea-c993b3f1f76b
caps.latest.revision: 10
ms.openlocfilehash: 1bc936b94ee6fd6239e9e3c4afcdb8f14fbe36eb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369075"
---
# <a name="alignment-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="91a2b-102">Elemento Alignment para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="91a2b-102">Alignment Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="91a2b-103">Define como os dados em uma coluna da linha são exibidos.</span><span class="sxs-lookup"><span data-stu-id="91a2b-103">Defines how the data in a column of the row is displayed.</span></span>

<span data-ttu-id="91a2b-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) TableColumnItems elemento (Format) TableColumnItem Element (Format) Elemento Alignment para TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="91a2b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) Alignment Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91a2b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91a2b-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91a2b-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="91a2b-106">Attributes and Elements</span></span>

<span data-ttu-id="91a2b-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Alignment`.</span><span class="sxs-lookup"><span data-stu-id="91a2b-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91a2b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="91a2b-108">Attributes</span></span>

<span data-ttu-id="91a2b-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="91a2b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91a2b-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="91a2b-110">Child Elements</span></span>

<span data-ttu-id="91a2b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="91a2b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91a2b-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="91a2b-112">Parent Elements</span></span>

|<span data-ttu-id="91a2b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="91a2b-113">Element</span></span>|<span data-ttu-id="91a2b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="91a2b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91a2b-115">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="91a2b-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="91a2b-116">Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="91a2b-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="91a2b-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="91a2b-117">Text Value</span></span>

<span data-ttu-id="91a2b-118">Especifique um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="91a2b-118">Specify one of the following values.</span></span> <span data-ttu-id="91a2b-119">(Esses valores não diferenciam maiúsculas de minúsculas.)</span><span class="sxs-lookup"><span data-stu-id="91a2b-119">(These values are not case-sensitive.)</span></span>

<span data-ttu-id="91a2b-120">A esquerda desloca os dados exibidos na coluna para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="91a2b-120">Left Shifts the data displayed in the column to the left.</span></span> <span data-ttu-id="91a2b-121">(Esse é o padrão se esse elemento não for especificado.)</span><span class="sxs-lookup"><span data-stu-id="91a2b-121">(This is the default if this element is not specified.)</span></span>

<span data-ttu-id="91a2b-122">A direita desloca os dados exibidos na coluna para a direita.</span><span class="sxs-lookup"><span data-stu-id="91a2b-122">Right Shifts the data displayed in the column to the right.</span></span>

<span data-ttu-id="91a2b-123">Centraliza os dados exibidos na coluna.</span><span class="sxs-lookup"><span data-stu-id="91a2b-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="91a2b-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="91a2b-124">Remarks</span></span>

<span data-ttu-id="91a2b-125">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="91a2b-125">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="91a2b-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91a2b-126">See Also</span></span>

[<span data-ttu-id="91a2b-127">Exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="91a2b-127">Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="91a2b-128">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="91a2b-128">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)
