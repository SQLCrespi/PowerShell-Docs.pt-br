---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para TableColumnItem para TableControl (formato)
description: Elemento PropertyName para TableColumnItem para TableControl (formato)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665576"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="c10fc-103">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c10fc-103">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="c10fc-104">Especifica a propriedade cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="c10fc-104">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="c10fc-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c10fc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c10fc-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c10fc-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c10fc-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="c10fc-107">Attributes and Elements</span></span>

<span data-ttu-id="c10fc-108">As seções a seguir descrevem atributos, elementos filho e elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="c10fc-108">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c10fc-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c10fc-109">Attributes</span></span>

<span data-ttu-id="c10fc-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="c10fc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c10fc-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="c10fc-111">Child Elements</span></span>

<span data-ttu-id="c10fc-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="c10fc-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c10fc-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="c10fc-113">Parent Elements</span></span>

|<span data-ttu-id="c10fc-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c10fc-114">Element</span></span>|<span data-ttu-id="c10fc-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="c10fc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c10fc-116">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c10fc-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="c10fc-117">Define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="c10fc-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c10fc-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="c10fc-118">Text Value</span></span>

<span data-ttu-id="c10fc-119">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="c10fc-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="c10fc-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="c10fc-120">Remarks</span></span>

<span data-ttu-id="c10fc-121">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="c10fc-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c10fc-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c10fc-122">Example</span></span>

<span data-ttu-id="c10fc-123">Este exemplo mostra um `TableColumnItem` elemento que especifica a `Status` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="c10fc-123">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="c10fc-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c10fc-124">See Also</span></span>

[<span data-ttu-id="c10fc-125">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="c10fc-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c10fc-126">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c10fc-126">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="c10fc-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c10fc-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
