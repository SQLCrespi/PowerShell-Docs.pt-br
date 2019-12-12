---
title: Elemento PropertyName para TableColumnItem para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26d72c-2f77-4801-badf-0537ccc55e31
caps.latest.revision: 10
ms.openlocfilehash: 6e86b6a0874b385703121802bc8108a0410442cd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362245"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="d4627-102">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="d4627-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="d4627-103">Especifica a propriedade cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="d4627-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="d4627-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) TableColumnItems elemento (Format) TableColumnItem Element (Format) Elemento PropertyName para TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="d4627-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d4627-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d4627-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4627-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d4627-106">Attributes and Elements</span></span>

<span data-ttu-id="d4627-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="d4627-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4627-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d4627-108">Attributes</span></span>

<span data-ttu-id="d4627-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d4627-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d4627-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="d4627-110">Child Elements</span></span>

<span data-ttu-id="d4627-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d4627-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d4627-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="d4627-112">Parent Elements</span></span>

|<span data-ttu-id="d4627-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4627-113">Element</span></span>|<span data-ttu-id="d4627-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4627-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4627-115">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="d4627-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="d4627-116">Define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="d4627-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d4627-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="d4627-117">Text Value</span></span>

<span data-ttu-id="d4627-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="d4627-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4627-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="d4627-119">Remarks</span></span>

<span data-ttu-id="d4627-120">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d4627-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d4627-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d4627-121">Example</span></span>

<span data-ttu-id="d4627-122">Este exemplo mostra um elemento `TableColumnItem` que especifica a propriedade `Status` do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="d4627-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="d4627-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4627-123">See Also</span></span>

[<span data-ttu-id="d4627-124">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="d4627-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d4627-125">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="d4627-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="d4627-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4627-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
