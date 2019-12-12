---
title: Elemento TableRowEntries para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: 88de19be02de4933f892e02093403a82ccdd5788
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368145"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="307b9-102">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="307b9-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="307b9-103">Define as linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="307b9-103">Defines the rows of the table.</span></span>

<span data-ttu-id="307b9-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento TableControl Element (Format) TableRowEntries elemento para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="307b9-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="307b9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="307b9-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="307b9-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="307b9-106">Attributes and Elements</span></span>

<span data-ttu-id="307b9-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `TableRowEntries`.</span><span class="sxs-lookup"><span data-stu-id="307b9-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="307b9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="307b9-108">Attributes</span></span>

<span data-ttu-id="307b9-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="307b9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="307b9-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="307b9-110">Child Elements</span></span>

|<span data-ttu-id="307b9-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="307b9-111">Element</span></span>|<span data-ttu-id="307b9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="307b9-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="307b9-113">Elemento TableRowEntry para TableRowEntries para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="307b9-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="307b9-114">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="307b9-114">Required element.</span></span><br /><br /> <span data-ttu-id="307b9-115">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="307b9-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="307b9-116">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="307b9-116">Parent Elements</span></span>

|<span data-ttu-id="307b9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="307b9-117">Element</span></span>|<span data-ttu-id="307b9-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="307b9-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="307b9-119">Elemento TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="307b9-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="307b9-120">Define um formato de tabela para uma exibição.</span><span class="sxs-lookup"><span data-stu-id="307b9-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="307b9-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="307b9-121">Remarks</span></span>

<span data-ttu-id="307b9-122">Você deve especificar um ou mais elementos de `TableRowEntry` para a exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="307b9-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="307b9-123">Não há nenhum limite máximo para o número de elementos `TableRowEntry` que podem ser adicionados, nem sua ordem é significativa.</span><span class="sxs-lookup"><span data-stu-id="307b9-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="307b9-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="307b9-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="307b9-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="307b9-125">Example</span></span>

<span data-ttu-id="307b9-126">O exemplo a seguir mostra um elemento `TableRowEntries` que define uma linha que exibe os valores de duas propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="307b9-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="307b9-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="307b9-127">See Also</span></span>

[<span data-ttu-id="307b9-128">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="307b9-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="307b9-129">Elemento TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="307b9-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="307b9-130">Elemento TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="307b9-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="307b9-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="307b9-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
