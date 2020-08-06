---
title: Elemento TableColumnItems para TableRowEntry para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 661b938e8db0e68e10dc05f552e4f3a14608bc55
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785142"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="9e692-102">Elemento TableColumnItems para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9e692-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="9e692-103">Define as propriedades ou os scripts cujos valores são exibidos em uma linha.</span><span class="sxs-lookup"><span data-stu-id="9e692-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="9e692-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) TableControl Element (Format) TableRowEntries elemento para TableControl (Format) TableRowEntry Element para TableRowEntries para TableControl (Format) TableColumnItems Element para TableControlEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9e692-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9e692-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9e692-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e692-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9e692-106">Attributes and Elements</span></span>

<span data-ttu-id="9e692-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TableColumnItems` elemento.</span><span class="sxs-lookup"><span data-stu-id="9e692-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e692-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9e692-108">Attributes</span></span>

<span data-ttu-id="9e692-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9e692-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9e692-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9e692-110">Child Elements</span></span>

|<span data-ttu-id="9e692-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e692-111">Element</span></span>|<span data-ttu-id="9e692-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e692-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e692-113">Elemento TableColumnItem para TableColumnItems para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9e692-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="9e692-114">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="9e692-114">Required element.</span></span><br /><br /> <span data-ttu-id="9e692-115">Define a propriedade ou o script cujo valor é exibido em uma coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="9e692-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9e692-116">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9e692-116">Parent Elements</span></span>

|<span data-ttu-id="9e692-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e692-117">Element</span></span>|<span data-ttu-id="9e692-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e692-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e692-119">Elemento TableRowEntry para TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9e692-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="9e692-120">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="9e692-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9e692-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="9e692-121">Remarks</span></span>

<span data-ttu-id="9e692-122">Um `TableColumnItem` elemento é necessário para cada coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="9e692-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="9e692-123">A primeira entrada é exibida na primeira coluna, a segunda entrada na segunda coluna e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="9e692-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="9e692-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="9e692-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9e692-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9e692-125">Example</span></span>

<span data-ttu-id="9e692-126">O exemplo a seguir mostra um `TableColumnItems` elemento que define três propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="9e692-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="9e692-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9e692-127">See Also</span></span>

[<span data-ttu-id="9e692-128">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="9e692-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9e692-129">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="9e692-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="9e692-130">Elemento TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="9e692-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="9e692-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e692-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
