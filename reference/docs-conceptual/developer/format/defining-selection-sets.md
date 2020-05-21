---
title: Definindo conjuntos de seleção | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 95eeb037b3b9190fec1212a68029624993f3fd9f
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692287"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="58514-102">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="58514-102">Defining Selection Sets</span></span>

<span data-ttu-id="58514-103">Ao criar vários modos de exibição e controles, você pode definir conjuntos de objetos que são chamados de conjuntos de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-103">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="58514-104">Um conjunto de seleção permite que você defina os objetos uma vez, sem precisar defini-los repetidamente para cada exibição ou controle.</span><span class="sxs-lookup"><span data-stu-id="58514-104">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="58514-105">Normalmente, os conjuntos de seleção são usados quando você tem um conjunto de objetos .NET relacionados.</span><span class="sxs-lookup"><span data-stu-id="58514-105">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="58514-106">Por exemplo, o `FileSystem` arquivo de formatação (FileSystem. Format. ps1xml) define um conjunto de seleção dos tipos de sistema de arquivos que várias exibições usam.</span><span class="sxs-lookup"><span data-stu-id="58514-106">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="58514-107">Onde os conjuntos de seleção são definidos e referenciados</span><span class="sxs-lookup"><span data-stu-id="58514-107">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="58514-108">Você define conjuntos de seleção como parte dos dados comuns que podem ser usados por todos os modos de exibição e controles definidos no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="58514-108">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="58514-109">O exemplo a seguir mostra como definir três conjuntos de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-109">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="58514-110">Você pode fazer referência a um conjunto de seleção das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="58514-110">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="58514-111">Cada exibição tem um `ViewSelectedBy` elemento que define quais objetos são exibidos usando a exibição.</span><span class="sxs-lookup"><span data-stu-id="58514-111">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="58514-112">O `ViewSelectedBy` elemento tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção que todas as definições da exibição usam.</span><span class="sxs-lookup"><span data-stu-id="58514-112">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="58514-113">Não há nenhuma restrição quanto ao número de conjuntos de seleção que você pode referenciar em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="58514-113">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="58514-114">Em cada definição de um modo de exibição ou controle, o `EntrySelectedBy` elemento define quais objetos são exibidos usando essa definição.</span><span class="sxs-lookup"><span data-stu-id="58514-114">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="58514-115">Normalmente, um modo de exibição ou controle tem apenas uma definição para que os objetos sejam definidos pelo `ViewSelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="58514-115">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="58514-116">O `EntrySelectedBy` elemento da definição tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-116">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="58514-117">Se você especificar o conjunto de seleção para uma definição, não poderá especificar nenhum dos outros elementos filho do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="58514-117">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="58514-118">Em cada definição de um modo de exibição ou controle, o `SelectionCondition` elemento pode ser usado para especificar uma condição para quando a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="58514-118">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="58514-119">O `SelectionCondition` elemento tem um `SelectionSetName` elemento filho que especifica o conjunto de seleção que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="58514-119">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="58514-120">A condição é disparada quando qualquer um dos objetos definidos no conjunto de seleção é exibido.</span><span class="sxs-lookup"><span data-stu-id="58514-120">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="58514-121">Para obter mais informações sobre como definir essas condições, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="58514-121">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="58514-122">Exemplo de conjunto de seleção</span><span class="sxs-lookup"><span data-stu-id="58514-122">Selection Set Example</span></span>

<span data-ttu-id="58514-123">O exemplo a seguir mostra um conjunto de seleção que é obtido diretamente do `FileSystem` arquivo de formatação fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58514-123">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="58514-124">Para obter mais informações sobre outros arquivos de formatação do Windows PowerShell, consulte [arquivos de formatação do Windows PowerShell](./powershell-formatting-files.md).</span><span class="sxs-lookup"><span data-stu-id="58514-124">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

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

<span data-ttu-id="58514-125">O conjunto de seleção anterior é referenciado no `ViewSelectedBy` elemento de uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="58514-125">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

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

## <a name="xml-elements"></a><span data-ttu-id="58514-126">Elementos XML</span><span class="sxs-lookup"><span data-stu-id="58514-126">XML Elements</span></span>

 <span data-ttu-id="58514-127">Não há nenhum limite para o número de conjuntos de seleção que você pode definir.</span><span class="sxs-lookup"><span data-stu-id="58514-127">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="58514-128">Os seguintes elementos XML são usados para criar um conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-128">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="58514-129">O elemento [SelectionSets](./selectionsets-element-format.md) define os conjuntos de objetos .NET que são referenciados pelas exibições e pelos controles do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="58514-129">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="58514-130">O elemento [SelectionSet](./selectionset-element-format.md) define um único conjunto de objetos .net.</span><span class="sxs-lookup"><span data-stu-id="58514-130">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="58514-131">O elemento [Name](./name-element-for-selectionset-format.md) especifica o nome que é usado para referenciar o conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-131">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="58514-132">O elemento [Types](./types-element-for-selectionset-format.md) especifica os tipos .net dos objetos do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-132">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="58514-133">(Em arquivos de formatação, os objetos são especificados por seu tipo .NET.)</span><span class="sxs-lookup"><span data-stu-id="58514-133">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="58514-134">Os seguintes elementos XML são usados para especificar um conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-134">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="58514-135">O elemento a seguir especifica o conjunto de seleção a ser usado em todas as definições da exibição:</span><span class="sxs-lookup"><span data-stu-id="58514-135">The following element specifies the selection set to use in all the definitions of the view:</span></span>

  - [<span data-ttu-id="58514-136">Elemento SelectionSetName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-136">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

  - [<span data-ttu-id="58514-137">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-137">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="58514-138">Os elementos a seguir especificam o conjunto de seleção usado por uma única definição de exibição:</span><span class="sxs-lookup"><span data-stu-id="58514-138">The following elements specify the selection set used by a single view definition:</span></span>

  - [<span data-ttu-id="58514-139">Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-139">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="58514-140">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-140">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="58514-141">Elemento SelectionSetName para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-141">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="58514-142">Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-142">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="58514-143">Os elementos a seguir especificam o conjunto de seleção usado pelas definições de controle comum e de exibição:</span><span class="sxs-lookup"><span data-stu-id="58514-143">The following elements specify the selection set used by common and view control definitions:</span></span>

  - [<span data-ttu-id="58514-144">Elemento SelectionSetName para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-144">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [<span data-ttu-id="58514-145">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-145">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="58514-146">Os seguintes elementos especificam o conjunto de seleção usado quando você define qual objeto expandir:</span><span class="sxs-lookup"><span data-stu-id="58514-146">The following elements specify the selection set used when you define which object to expand:</span></span>

  - [<span data-ttu-id="58514-147">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-147">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="58514-148">Os elementos a seguir especificam o conjunto de seleção usado por condições de seleção.</span><span class="sxs-lookup"><span data-stu-id="58514-148">The following elements specify the selection set used by selection conditions.</span></span>

  - [<span data-ttu-id="58514-149">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-149">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="58514-150">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-150">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [<span data-ttu-id="58514-151">Elemento SelectionSetName para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-151">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [<span data-ttu-id="58514-152">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-152">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [<span data-ttu-id="58514-153">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [<span data-ttu-id="58514-154">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="58514-155">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [<span data-ttu-id="58514-156">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="58514-156">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="58514-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58514-157">See Also</span></span>

[<span data-ttu-id="58514-158">SelectionSets</span><span class="sxs-lookup"><span data-stu-id="58514-158">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="58514-159">Selecionador de seleção</span><span class="sxs-lookup"><span data-stu-id="58514-159">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="58514-160">Nome</span><span class="sxs-lookup"><span data-stu-id="58514-160">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="58514-161">Tipos</span><span class="sxs-lookup"><span data-stu-id="58514-161">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="58514-162">Arquivos de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58514-162">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="58514-163">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="58514-163">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="58514-164">Gravando um arquivo de tipos e formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58514-164">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
