---
title: Elemento EntrySelectedBy para TableRowEntry para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 047a10fb6b38dfa8f78a7741fd50b781d4a14b6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787692"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="a56e2-102">Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a56e2-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="a56e2-103">Define os tipos .NET que usam essa definição da exibição de tabela ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="a56e2-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="a56e2-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento TableControl (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a56e2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a56e2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a56e2-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a56e2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a56e2-106">Attributes and Elements</span></span>

<span data-ttu-id="a56e2-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="a56e2-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a56e2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a56e2-108">Attributes</span></span>

<span data-ttu-id="a56e2-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a56e2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a56e2-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a56e2-110">Child Elements</span></span>

|<span data-ttu-id="a56e2-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a56e2-111">Element</span></span>|<span data-ttu-id="a56e2-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a56e2-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a56e2-113">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a56e2-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="a56e2-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a56e2-114">Optional element.</span></span><br /><br /> <span data-ttu-id="a56e2-115">Define a condição que deve existir para esta definição de exibição de tabela a ser usada.</span><span class="sxs-lookup"><span data-stu-id="a56e2-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="a56e2-116">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a56e2-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="a56e2-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a56e2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a56e2-118">Especifica um conjunto de tipos .NET que usam esta definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="a56e2-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="a56e2-119">Elemento TypeName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a56e2-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="a56e2-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a56e2-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a56e2-121">Especifica um tipo .NET que usa esta definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="a56e2-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a56e2-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a56e2-122">Parent Elements</span></span>

|<span data-ttu-id="a56e2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="a56e2-123">Element</span></span>|<span data-ttu-id="a56e2-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="a56e2-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a56e2-125">Elemento TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a56e2-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="a56e2-126">Define os dados que são exibidos em uma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="a56e2-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a56e2-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="a56e2-127">Remarks</span></span>

<span data-ttu-id="a56e2-128">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="a56e2-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="a56e2-129">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="a56e2-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a56e2-130">As condições de seleção são usadas para definir uma condição que deve existir para que a definição seja usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="a56e2-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a56e2-131">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a56e2-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a56e2-132">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="a56e2-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a56e2-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a56e2-133">Example</span></span>

<span data-ttu-id="a56e2-134">O exemplo a seguir mostra um `TableRowEntry` elemento que é usado para exibir as propriedades do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="a56e2-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a56e2-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a56e2-135">See Also</span></span>

[<span data-ttu-id="a56e2-136">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="a56e2-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a56e2-137">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a56e2-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="a56e2-138">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a56e2-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="a56e2-139">Elemento TableRowEntry para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a56e2-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="a56e2-140">Elemento TypeName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a56e2-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="a56e2-141">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a56e2-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
