---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableRowEntries para TableControl (formato)
description: Elemento TableRowEntries para TableControl (formato)
ms.openlocfilehash: 1df63e645234da8276c7ccc5af34e81a56475e43
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651475"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="ef0a9-103">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="ef0a9-103">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="ef0a9-104">Define as linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-104">Defines the rows of the table.</span></span>

<span data-ttu-id="ef0a9-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento TableControl Element (Format) TableRowEntries elemento para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ef0a9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ef0a9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ef0a9-106">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ef0a9-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ef0a9-107">Attributes and Elements</span></span>

<span data-ttu-id="ef0a9-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TableRowEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-108">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef0a9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef0a9-109">Attributes</span></span>

<span data-ttu-id="ef0a9-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ef0a9-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ef0a9-111">Child Elements</span></span>

|<span data-ttu-id="ef0a9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef0a9-112">Element</span></span>|<span data-ttu-id="ef0a9-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="ef0a9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef0a9-114">Elemento TableRowEntry para TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="ef0a9-114">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="ef0a9-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-115">Required element.</span></span><br /><br /> <span data-ttu-id="ef0a9-116">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-116">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ef0a9-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ef0a9-117">Parent Elements</span></span>

|<span data-ttu-id="ef0a9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef0a9-118">Element</span></span>|<span data-ttu-id="ef0a9-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="ef0a9-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef0a9-120">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="ef0a9-120">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="ef0a9-121">Define um formato de tabela para uma exibição.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-121">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ef0a9-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="ef0a9-122">Remarks</span></span>

<span data-ttu-id="ef0a9-123">Você deve especificar um ou mais `TableRowEntry` elementos para a exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-123">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="ef0a9-124">Não há nenhum limite máximo para o número de `TableRowEntry` elementos que podem ser adicionados, nem sua ordem significativa.</span><span class="sxs-lookup"><span data-stu-id="ef0a9-124">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="ef0a9-125">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="ef0a9-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ef0a9-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ef0a9-126">Example</span></span>

<span data-ttu-id="ef0a9-127">O exemplo a seguir mostra um `TableRowEntries` elemento que define uma linha que exibe os valores de duas propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="ef0a9-127">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a><span data-ttu-id="ef0a9-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef0a9-128">See Also</span></span>

[<span data-ttu-id="ef0a9-129">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="ef0a9-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ef0a9-130">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="ef0a9-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="ef0a9-131">Elemento TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ef0a9-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="ef0a9-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef0a9-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
