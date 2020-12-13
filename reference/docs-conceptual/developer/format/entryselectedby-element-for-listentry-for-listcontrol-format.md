---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para ListEntry para ListControl (formato)
description: Elemento EntrySelectedBy para ListEntry para ListControl (formato)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652291"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="4dc0f-103">Elemento EntrySelectedBy para ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-103">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="4dc0f-104">Define os tipos .NET que usam essa definição de exibição de lista ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-104">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="4dc0f-105">Na maioria dos casos, apenas uma definição é necessária para uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-105">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="4dc0f-106">No entanto, você pode fornecer várias definições para o modo de exibição de lista se quiser usar a mesma exibição de lista para exibir dados diferentes para objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-106">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="4dc0f-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntry para o elemento ListControl (Format) EntrySelectedBy para ListEntry para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4dc0f-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4dc0f-108">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4dc0f-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4dc0f-109">Attributes and Elements</span></span>

<span data-ttu-id="4dc0f-110">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-110">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4dc0f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4dc0f-111">Attributes</span></span>

<span data-ttu-id="4dc0f-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4dc0f-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="4dc0f-113">Child Elements</span></span>

|<span data-ttu-id="4dc0f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dc0f-114">Element</span></span>|<span data-ttu-id="4dc0f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="4dc0f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4dc0f-116">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-116">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4dc0f-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4dc0f-118">Define a condição que deve existir para esta definição de exibição de lista ser usada.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-118">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="4dc0f-119">Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-119">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4dc0f-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4dc0f-121">Especifica um conjunto de tipos .NET que usam esta definição de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-121">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="4dc0f-122">Elemento TypeName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-122">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4dc0f-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4dc0f-124">Especifica um tipo .NET que usa essa definição de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-124">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4dc0f-125">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="4dc0f-125">Parent Elements</span></span>

|<span data-ttu-id="4dc0f-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dc0f-126">Element</span></span>|<span data-ttu-id="4dc0f-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="4dc0f-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4dc0f-128">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="4dc0f-129">Define como as linhas da lista são exibidas.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-129">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4dc0f-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="4dc0f-130">Remarks</span></span>

<span data-ttu-id="4dc0f-131">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-131">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="4dc0f-132">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-132">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="4dc0f-133">As condições de seleção são usadas para definir uma condição que deve existir para que a definição seja usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="4dc0f-133">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="4dc0f-134">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4dc0f-134">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4dc0f-135">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="4dc0f-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4dc0f-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4dc0f-136">Example</span></span>

<span data-ttu-id="4dc0f-137">O exemplo a seguir mostra como definir os objetos para um modo de exibição de lista usando o nome do tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-137">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="4dc0f-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4dc0f-138">See Also</span></span>

[<span data-ttu-id="4dc0f-139">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-139">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="4dc0f-140">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-140">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4dc0f-141">Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-141">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4dc0f-142">Elemento TypeName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="4dc0f-142">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4dc0f-143">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="4dc0f-143">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4dc0f-144">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="4dc0f-144">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4dc0f-145">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dc0f-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
