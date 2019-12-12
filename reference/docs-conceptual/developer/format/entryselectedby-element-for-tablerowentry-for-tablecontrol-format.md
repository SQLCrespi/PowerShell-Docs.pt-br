---
title: Elemento EntrySelectedBy para TableRowEntry para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363335"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="67cf4-102">Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="67cf4-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="67cf4-103">Define os tipos .NET que usam essa definição da exibição de tabela ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="67cf4-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="67cf4-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento TableControl (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="67cf4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="67cf4-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="67cf4-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="67cf4-106">Attributes and Elements</span></span>

<span data-ttu-id="67cf4-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="67cf4-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="67cf4-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="67cf4-108">Attributes</span></span>

<span data-ttu-id="67cf4-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="67cf4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="67cf4-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="67cf4-110">Child Elements</span></span>

|<span data-ttu-id="67cf4-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="67cf4-111">Element</span></span>|<span data-ttu-id="67cf4-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="67cf4-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67cf4-113">Elemento SelectionCondition para EntrySelectedBy para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="67cf4-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="67cf4-114">Optional element.</span></span><br /><br /> <span data-ttu-id="67cf4-115">Define a condição que deve existir para esta definição de exibição de tabela a ser usada.</span><span class="sxs-lookup"><span data-stu-id="67cf4-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="67cf4-116">Elemento SelectionSetName para EntrySelectedBy para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="67cf4-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="67cf4-117">Optional element.</span></span><br /><br /> <span data-ttu-id="67cf4-118">Especifica um conjunto de tipos .NET que usam esta definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="67cf4-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="67cf4-119">Elemento TypeName para EntrySelectedBy para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="67cf4-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="67cf4-120">Optional element.</span></span><br /><br /> <span data-ttu-id="67cf4-121">Especifica um tipo .NET que usa esta definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="67cf4-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="67cf4-122">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="67cf4-122">Parent Elements</span></span>

|<span data-ttu-id="67cf4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="67cf4-123">Element</span></span>|<span data-ttu-id="67cf4-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="67cf4-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67cf4-125">Elemento TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="67cf4-126">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="67cf4-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="67cf4-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="67cf4-127">Remarks</span></span>

<span data-ttu-id="67cf4-128">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="67cf4-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="67cf4-129">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="67cf4-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="67cf4-130">As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true`.</span><span class="sxs-lookup"><span data-stu-id="67cf4-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="67cf4-131">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="67cf4-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="67cf4-132">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="67cf4-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="67cf4-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="67cf4-133">Example</span></span>

<span data-ttu-id="67cf4-134">O exemplo a seguir mostra um elemento `TableRowEntry` que é usado para exibir as propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="67cf4-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="67cf4-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67cf4-135">See Also</span></span>

[<span data-ttu-id="67cf4-136">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="67cf4-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="67cf4-137">Elemento SelectionCondition para EntrySelectedBy para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="67cf4-138">Elemento SelectionSetName para EntrySelectedBy para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="67cf4-139">Elemento TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="67cf4-140">Elemento TypeName para EntrySelectedBy para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="67cf4-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="67cf4-141">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="67cf4-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
