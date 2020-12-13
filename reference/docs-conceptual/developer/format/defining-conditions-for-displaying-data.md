---
ms.date: 09/13/2016
ms.topic: reference
title: Definir condições para a exibição de dados
description: Definir condições para a exibição de dados
ms.openlocfilehash: 9a8b7a618da8c64de978c13b527435a2d7793677
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660313"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="2bb3f-103">Definir condições para a exibição de dados</span><span class="sxs-lookup"><span data-stu-id="2bb3f-103">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="2bb3f-104">Ao definir quais dados são exibidos por uma exibição ou um controle, você pode especificar uma condição que deve existir para que os dados sejam exibidos.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-104">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="2bb3f-105">A condição pode ser disparada por uma propriedade específica ou quando um valor de script ou propriedade é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="2bb3f-105">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="2bb3f-106">Quando a condição de seleção é atendida, a definição da exibição ou do controle é usada.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-106">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="2bb3f-107">Especificando uma condição de seleção para uma definição</span><span class="sxs-lookup"><span data-stu-id="2bb3f-107">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="2bb3f-108">Ao criar uma definição para um modo de exibição ou controle, o `EntrySelectedBy` elemento é usado para especificar quais objetos usarão a definição ou qual condição deve existir para que a definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-108">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="2bb3f-109">A condição é especificada pelo `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-109">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="2bb3f-110">No exemplo a seguir, uma condição de seleção é especificada para uma definição de uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-110">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="2bb3f-111">Neste exemplo, a definição é usada somente quando o script especificado é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="2bb3f-111">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

<span data-ttu-id="2bb3f-112">Não há nenhum limite para o número de condições de seleção que você pode especificar para uma definição de um modo de exibição ou controle.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-112">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="2bb3f-113">Os únicos requisitos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="2bb3f-113">The only requirements are the following:</span></span>

- <span data-ttu-id="2bb3f-114">A condição de seleção deve especificar um nome de propriedade ou script para disparar a condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-114">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="2bb3f-115">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-115">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="2bb3f-116">Especificando uma condição de seleção para um item</span><span class="sxs-lookup"><span data-stu-id="2bb3f-116">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="2bb3f-117">Você também pode especificar quando um item de um modo de exibição de lista ou controle é usado incluindo o `ItemSelectionCondition` elemento na definição de item.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-117">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="2bb3f-118">No exemplo a seguir, uma condição de seleção é especificada para um item de um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-118">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="2bb3f-119">Neste exemplo, o item é usado somente quando o script é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="2bb3f-119">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="2bb3f-120">Você pode especificar apenas uma condição de seleção para um item.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-120">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="2bb3f-121">E a condição deve especificar um nome de propriedade ou script para disparar a condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-121">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="2bb3f-122">Elementos XML</span><span class="sxs-lookup"><span data-stu-id="2bb3f-122">XML Elements</span></span>

 <span data-ttu-id="2bb3f-123">Os seguintes elementos XML são usados para criar uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="2bb3f-123">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="2bb3f-124">Os elementos a seguir especificam as condições de seleção para definições de exibição:</span><span class="sxs-lookup"><span data-stu-id="2bb3f-124">The following elements specify selection conditions for view definitions:</span></span>

  - [<span data-ttu-id="2bb3f-125">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-125">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="2bb3f-126">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-126">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="2bb3f-127">Elemento SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-127">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="2bb3f-128">Elemento SelectionCondition para EntrySelectedBy para CustomControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-128">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="2bb3f-129">Os elementos a seguir especificam as condições de seleção para as definições de controle comum e de exibição:</span><span class="sxs-lookup"><span data-stu-id="2bb3f-129">The following elements specify selection conditions for common and view control definitions:</span></span>

  - [<span data-ttu-id="2bb3f-130">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-130">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="2bb3f-131">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-131">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="2bb3f-132">O elemento a seguir especifica a condição de seleção para expandir objetos de coleção:</span><span class="sxs-lookup"><span data-stu-id="2bb3f-132">The following element specifies the selection condition for expanding collection objects:</span></span>

  - [<span data-ttu-id="2bb3f-133">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-133">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="2bb3f-134">O elemento a seguir especifica a condição de seleção para exibir um novo grupo de dados:</span><span class="sxs-lookup"><span data-stu-id="2bb3f-134">The following element specifies the selection condition for displaying a new group of data:</span></span>

  - [<span data-ttu-id="2bb3f-135">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="2bb3f-136">O elemento a seguir especifica uma condição de seleção de item para uma exibição de lista:</span><span class="sxs-lookup"><span data-stu-id="2bb3f-136">The following element specifies an item selection condition for a list view:</span></span>

  - [<span data-ttu-id="2bb3f-137">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-137">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="2bb3f-138">Os elementos a seguir especificam uma condição de seleção de item para controles:</span><span class="sxs-lookup"><span data-stu-id="2bb3f-138">The following elements specify an item selection condition for controls:</span></span>

  - [<span data-ttu-id="2bb3f-139">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-139">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="2bb3f-140">Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-140">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [<span data-ttu-id="2bb3f-141">Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2bb3f-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="2bb3f-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2bb3f-142">See Also</span></span>

[<span data-ttu-id="2bb3f-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bb3f-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
