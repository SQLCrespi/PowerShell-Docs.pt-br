---
title: Elemento de alinhamento para TableColumnHeader para TableControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff85e83a-c9c2-4c37-accc-e6a27c182f3c
caps.latest.revision: 19
ms.openlocfilehash: 16b41535109ca503e679a135f5ba30054e33de5b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067001"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="eb2fd-102">Elemento Alignment para TableColumnHeader para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="eb2fd-102">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="eb2fd-103">Define como os dados em um cabeçalho de coluna são exibidos.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-103">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="eb2fd-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento TableControl (formato) elemento TableHeaders (formato) elemento TableColumnHeader (formato) alinhamento elemento de configuração para TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="eb2fd-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eb2fd-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eb2fd-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eb2fd-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="eb2fd-106">Attributes and Elements</span></span>

<span data-ttu-id="eb2fd-107">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `Alignment` elemento.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="eb2fd-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="eb2fd-108">Attributes</span></span>

<span data-ttu-id="eb2fd-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eb2fd-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="eb2fd-110">Child Elements</span></span>

<span data-ttu-id="eb2fd-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eb2fd-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="eb2fd-112">Parent Elements</span></span>

|<span data-ttu-id="eb2fd-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb2fd-113">Element</span></span>|<span data-ttu-id="eb2fd-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb2fd-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eb2fd-115">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="eb2fd-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="eb2fd-116">Define um rótulo, a largura e o alinhamento dos dados para uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="eb2fd-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="eb2fd-117">Text Value</span></span>

<span data-ttu-id="eb2fd-118">Especifique um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-118">Specify one of the following values.</span></span> <span data-ttu-id="eb2fd-119">Esses valores não diferenciam maiusculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-119">These values are not case-sensitive.</span></span>

<span data-ttu-id="eb2fd-120">Isso alinha à esquerda os dados exibidos na coluna à esquerda é o padrão se esse elemento não for especificado.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-120">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="eb2fd-121">Alinha à direita os dados exibidos na coluna à direita.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-121">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="eb2fd-122">Centros de centro de dados exibidos na coluna.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-122">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb2fd-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="eb2fd-123">Remarks</span></span>

<span data-ttu-id="eb2fd-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="eb2fd-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="eb2fd-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eb2fd-125">Example</span></span>

<span data-ttu-id="eb2fd-126">Este exemplo mostra um `TableColumnHeader` cujos dados são alinhados à esquerda do elemento.</span><span class="sxs-lookup"><span data-stu-id="eb2fd-126">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="eb2fd-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb2fd-127">See Also</span></span>

[<span data-ttu-id="eb2fd-128">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="eb2fd-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="eb2fd-129">Elemento TableColumnHeader (formato)</span><span class="sxs-lookup"><span data-stu-id="eb2fd-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="eb2fd-130">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb2fd-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
