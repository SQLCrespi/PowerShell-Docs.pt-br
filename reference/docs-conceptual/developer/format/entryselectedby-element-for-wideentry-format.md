---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para WideEntry (formato)
description: Elemento EntrySelectedBy para WideEntry (formato)
ms.openlocfilehash: 246a1967300ab0551f376c4799deac275068308c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660241"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="fbed7-103">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="fbed7-103">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="fbed7-104">Define os tipos .NET que usam essa definição da exibição larga ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="fbed7-104">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="fbed7-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fbed7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fbed7-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fbed7-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fbed7-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fbed7-107">Attributes and Elements</span></span>

<span data-ttu-id="fbed7-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="fbed7-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fbed7-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fbed7-109">Attributes</span></span>

<span data-ttu-id="fbed7-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="fbed7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fbed7-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="fbed7-111">Child Elements</span></span>

|<span data-ttu-id="fbed7-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbed7-112">Element</span></span>|<span data-ttu-id="fbed7-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="fbed7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fbed7-114">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fbed7-114">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="fbed7-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="fbed7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="fbed7-116">Define a condição que deve existir para essa definição de exibição ampla ser usada.</span><span class="sxs-lookup"><span data-stu-id="fbed7-116">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="fbed7-117">Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fbed7-117">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="fbed7-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="fbed7-118">Optional element.</span></span><br /><br /> <span data-ttu-id="fbed7-119">Especifica um conjunto de tipos .NET que usam essa definição de exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="fbed7-119">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="fbed7-120">Elemento TypeName para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="fbed7-120">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="fbed7-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="fbed7-121">Optional element.</span></span><br /><br /> <span data-ttu-id="fbed7-122">Especifica um tipo .NET que usa essa definição de exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="fbed7-122">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fbed7-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="fbed7-123">Parent Elements</span></span>

|<span data-ttu-id="fbed7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbed7-124">Element</span></span>|<span data-ttu-id="fbed7-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="fbed7-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fbed7-126">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fbed7-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="fbed7-127">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="fbed7-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fbed7-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="fbed7-128">Remarks</span></span>

<span data-ttu-id="fbed7-129">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="fbed7-129">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="fbed7-130">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="fbed7-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="fbed7-131">As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou valor de script específico é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="fbed7-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="fbed7-132">Para obter mais informações sobre condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="fbed7-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="fbed7-133">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="fbed7-133">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fbed7-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fbed7-134">See Also</span></span>

[<span data-ttu-id="fbed7-135">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fbed7-135">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="fbed7-136">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fbed7-136">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="fbed7-137">Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fbed7-137">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="fbed7-138">Elemento TypeName para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="fbed7-138">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="fbed7-139">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="fbed7-139">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="fbed7-140">Definir condições para a exibição de dados</span><span class="sxs-lookup"><span data-stu-id="fbed7-140">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="fbed7-141">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbed7-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
