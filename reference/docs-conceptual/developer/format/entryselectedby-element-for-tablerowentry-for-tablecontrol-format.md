---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)
description: Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)
ms.openlocfilehash: 1b7fc60b6fa9864b66e9edfebb3e4a86e287f3f8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645898"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="83ee2-103">Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83ee2-103">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="83ee2-104">Define os tipos .NET que usam essa definição da exibição de tabela ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="83ee2-104">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="83ee2-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento TableControl (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="83ee2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="83ee2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="83ee2-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="83ee2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="83ee2-107">Attributes and Elements</span></span>

<span data-ttu-id="83ee2-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="83ee2-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="83ee2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="83ee2-109">Attributes</span></span>

<span data-ttu-id="83ee2-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="83ee2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="83ee2-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="83ee2-111">Child Elements</span></span>

|<span data-ttu-id="83ee2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="83ee2-112">Element</span></span>|<span data-ttu-id="83ee2-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="83ee2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83ee2-114">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83ee2-114">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="83ee2-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="83ee2-115">Optional element.</span></span><br /><br /> <span data-ttu-id="83ee2-116">Define a condição que deve existir para esta definição de exibição de tabela a ser usada.</span><span class="sxs-lookup"><span data-stu-id="83ee2-116">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="83ee2-117">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83ee2-117">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="83ee2-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="83ee2-118">Optional element.</span></span><br /><br /> <span data-ttu-id="83ee2-119">Especifica um conjunto de tipos .NET que usam esta definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="83ee2-119">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="83ee2-120">Elemento TypeName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83ee2-120">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="83ee2-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="83ee2-121">Optional element.</span></span><br /><br /> <span data-ttu-id="83ee2-122">Especifica um tipo .NET que usa esta definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="83ee2-122">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="83ee2-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="83ee2-123">Parent Elements</span></span>

|<span data-ttu-id="83ee2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="83ee2-124">Element</span></span>|<span data-ttu-id="83ee2-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="83ee2-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83ee2-126">Elemento TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="83ee2-126">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="83ee2-127">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="83ee2-127">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83ee2-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="83ee2-128">Remarks</span></span>

<span data-ttu-id="83ee2-129">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="83ee2-129">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="83ee2-130">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="83ee2-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="83ee2-131">As condições de seleção são usadas para definir uma condição que deve existir para que a definição seja usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="83ee2-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="83ee2-132">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="83ee2-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="83ee2-133">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="83ee2-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="83ee2-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="83ee2-134">Example</span></span>

<span data-ttu-id="83ee2-135">O exemplo a seguir mostra um `TableRowEntry` elemento que é usado para exibir as propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="83ee2-135">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="83ee2-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83ee2-136">See Also</span></span>

[<span data-ttu-id="83ee2-137">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="83ee2-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="83ee2-138">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83ee2-138">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="83ee2-139">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83ee2-139">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="83ee2-140">Elemento TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="83ee2-140">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="83ee2-141">Elemento TypeName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83ee2-141">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="83ee2-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="83ee2-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
