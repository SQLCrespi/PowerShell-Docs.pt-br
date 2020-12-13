---
ms.date: 09/13/2016
ms.topic: reference
title: Definir conjuntos de seleção
description: Definir conjuntos de seleção
ms.openlocfilehash: d709a368a45623d56fdbf4e98a11a5e5f8a193fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648262"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="c6475-103">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="c6475-103">Defining Selection Sets</span></span>

<span data-ttu-id="c6475-104">Ao criar vários modos de exibição e controles, você pode definir conjuntos de objetos que são chamados de conjuntos de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-104">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="c6475-105">Um conjunto de seleção permite que você defina os objetos uma vez, sem precisar defini-los repetidamente para cada exibição ou controle.</span><span class="sxs-lookup"><span data-stu-id="c6475-105">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="c6475-106">Normalmente, os conjuntos de seleção são usados quando você tem um conjunto de objetos .NET relacionados.</span><span class="sxs-lookup"><span data-stu-id="c6475-106">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="c6475-107">Por exemplo, o `FileSystem` arquivo de formatação (FileSystem.format.ps1XML) define um conjunto de seleção dos tipos de sistema de arquivos que várias exibições usam.</span><span class="sxs-lookup"><span data-stu-id="c6475-107">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="c6475-108">Onde os conjuntos de seleção são definidos e referenciados</span><span class="sxs-lookup"><span data-stu-id="c6475-108">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="c6475-109">Você define conjuntos de seleção como parte dos dados comuns que podem ser usados por todos os modos de exibição e controles definidos no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="c6475-109">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="c6475-110">O exemplo a seguir mostra como definir três conjuntos de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-110">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="c6475-111">Você pode fazer referência a um conjunto de seleção das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="c6475-111">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="c6475-112">Cada exibição tem um `ViewSelectedBy` elemento que define quais objetos são exibidos usando a exibição.</span><span class="sxs-lookup"><span data-stu-id="c6475-112">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="c6475-113">O `ViewSelectedBy` elemento tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção que todas as definições da exibição usam.</span><span class="sxs-lookup"><span data-stu-id="c6475-113">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="c6475-114">Não há nenhuma restrição quanto ao número de conjuntos de seleção que você pode referenciar em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="c6475-114">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="c6475-115">Em cada definição de um modo de exibição ou controle, o `EntrySelectedBy` elemento define quais objetos são exibidos usando essa definição.</span><span class="sxs-lookup"><span data-stu-id="c6475-115">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="c6475-116">Normalmente, um modo de exibição ou controle tem apenas uma definição para que os objetos sejam definidos pelo `ViewSelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="c6475-116">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="c6475-117">O `EntrySelectedBy` elemento da definição tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-117">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="c6475-118">Se você especificar o conjunto de seleção para uma definição, não poderá especificar nenhum dos outros elementos filho do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="c6475-118">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="c6475-119">Em cada definição de um modo de exibição ou controle, o `SelectionCondition` elemento pode ser usado para especificar uma condição para quando a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="c6475-119">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="c6475-120">O `SelectionCondition` elemento tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="c6475-120">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="c6475-121">A condição é disparada quando qualquer um dos objetos definidos no conjunto de seleção é exibido.</span><span class="sxs-lookup"><span data-stu-id="c6475-121">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="c6475-122">Para obter mais informações sobre como definir essas condições, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c6475-122">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="c6475-123">Exemplo de conjunto de seleção</span><span class="sxs-lookup"><span data-stu-id="c6475-123">Selection Set Example</span></span>

<span data-ttu-id="c6475-124">O exemplo a seguir mostra um conjunto de seleção que é obtido diretamente do `FileSystem` arquivo de formatação fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6475-124">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="c6475-125">Para obter mais informações sobre outros arquivos de formatação do Windows PowerShell, consulte [arquivos de formatação do Windows PowerShell](./powershell-formatting-files.md).</span><span class="sxs-lookup"><span data-stu-id="c6475-125">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

<span data-ttu-id="c6475-126">O conjunto de seleção anterior é referenciado no `ViewSelectedBy` elemento de uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="c6475-126">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a><span data-ttu-id="c6475-127">Elementos XML</span><span class="sxs-lookup"><span data-stu-id="c6475-127">XML Elements</span></span>

 <span data-ttu-id="c6475-128">Não há nenhum limite para o número de conjuntos de seleção que você pode definir.</span><span class="sxs-lookup"><span data-stu-id="c6475-128">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="c6475-129">Os seguintes elementos XML são usados para criar um conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-129">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="c6475-130">O elemento [SelectionSets](./selectionsets-element-format.md) define os conjuntos de objetos .NET que são referenciados pelas exibições e pelos controles do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="c6475-130">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="c6475-131">O elemento [SelectionSet](./selectionset-element-format.md) define um único conjunto de objetos .net.</span><span class="sxs-lookup"><span data-stu-id="c6475-131">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="c6475-132">O elemento [Name](./name-element-for-selectionset-format.md) especifica o nome que é usado para referenciar o conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-132">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="c6475-133">O elemento [Types](./types-element-for-selectionset-format.md) especifica os tipos .net dos objetos do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-133">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="c6475-134">(Em arquivos de formatação, os objetos são especificados por seu tipo .NET.)</span><span class="sxs-lookup"><span data-stu-id="c6475-134">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="c6475-135">Os seguintes elementos XML são usados para especificar um conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-135">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="c6475-136">O elemento a seguir especifica o conjunto de seleção a ser usado em todas as definições da exibição:</span><span class="sxs-lookup"><span data-stu-id="c6475-136">The following element specifies the selection set to use in all the definitions of the view:</span></span>

  - [<span data-ttu-id="c6475-137">Elemento SelectionSetName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-137">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

  - [<span data-ttu-id="c6475-138">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-138">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="c6475-139">Os elementos a seguir especificam o conjunto de seleção usado por uma única definição de exibição:</span><span class="sxs-lookup"><span data-stu-id="c6475-139">The following elements specify the selection set used by a single view definition:</span></span>

  - [<span data-ttu-id="c6475-140">Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="c6475-141">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-141">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="c6475-142">Elemento SelectionSetName para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-142">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="c6475-143">Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-143">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="c6475-144">Os elementos a seguir especificam o conjunto de seleção usado pelas definições de controle comum e de exibição:</span><span class="sxs-lookup"><span data-stu-id="c6475-144">The following elements specify the selection set used by common and view control definitions:</span></span>

  - [<span data-ttu-id="c6475-145">Elemento SelectionSetName para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-145">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [<span data-ttu-id="c6475-146">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-146">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="c6475-147">Os seguintes elementos especificam o conjunto de seleção usado quando você define qual objeto expandir:</span><span class="sxs-lookup"><span data-stu-id="c6475-147">The following elements specify the selection set used when you define which object to expand:</span></span>

  - [<span data-ttu-id="c6475-148">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-148">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="c6475-149">Os elementos a seguir especificam o conjunto de seleção usado por condições de seleção.</span><span class="sxs-lookup"><span data-stu-id="c6475-149">The following elements specify the selection set used by selection conditions.</span></span>

  - [<span data-ttu-id="c6475-150">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-150">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="c6475-151">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-151">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [<span data-ttu-id="c6475-152">Elemento SelectionSetName para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-152">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [<span data-ttu-id="c6475-153">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [<span data-ttu-id="c6475-154">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [<span data-ttu-id="c6475-155">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="c6475-156">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-156">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [<span data-ttu-id="c6475-157">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="c6475-157">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="c6475-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6475-158">See Also</span></span>

[<span data-ttu-id="c6475-159">SelectionSets</span><span class="sxs-lookup"><span data-stu-id="c6475-159">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="c6475-160">Selecionador de seleção</span><span class="sxs-lookup"><span data-stu-id="c6475-160">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="c6475-161">Nome</span><span class="sxs-lookup"><span data-stu-id="c6475-161">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="c6475-162">Types</span><span class="sxs-lookup"><span data-stu-id="c6475-162">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="c6475-163">Arquivos de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6475-163">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="c6475-164">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="c6475-164">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c6475-165">Gravando um arquivo de tipos e formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6475-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
