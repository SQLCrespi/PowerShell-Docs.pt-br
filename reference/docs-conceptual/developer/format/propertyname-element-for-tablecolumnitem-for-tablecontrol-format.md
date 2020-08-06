---
title: Elemento PropertyName para TableColumnItem para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bf267eeb83aef59abea2d945af12e849252309c8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772970"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="9b55e-102">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9b55e-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="9b55e-103">Especifica a propriedade cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="9b55e-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="9b55e-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="9b55e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b55e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b55e-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b55e-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9b55e-106">Attributes and Elements</span></span>

<span data-ttu-id="9b55e-107">As seções a seguir descrevem atributos, elementos filho e elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="9b55e-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b55e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b55e-108">Attributes</span></span>

<span data-ttu-id="9b55e-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9b55e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b55e-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9b55e-110">Child Elements</span></span>

<span data-ttu-id="9b55e-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9b55e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9b55e-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9b55e-112">Parent Elements</span></span>

|<span data-ttu-id="9b55e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b55e-113">Element</span></span>|<span data-ttu-id="9b55e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b55e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b55e-115">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="9b55e-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="9b55e-116">Define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="9b55e-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9b55e-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9b55e-117">Text Value</span></span>

<span data-ttu-id="9b55e-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="9b55e-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b55e-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="9b55e-119">Remarks</span></span>

<span data-ttu-id="9b55e-120">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="9b55e-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9b55e-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9b55e-121">Example</span></span>

<span data-ttu-id="9b55e-122">Este exemplo mostra um `TableColumnItem` elemento que especifica a `Status` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="9b55e-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="9b55e-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b55e-123">See Also</span></span>

[<span data-ttu-id="9b55e-124">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="9b55e-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9b55e-125">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="9b55e-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="9b55e-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b55e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
