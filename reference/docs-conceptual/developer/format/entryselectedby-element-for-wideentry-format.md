---
title: Elemento EntrySelectedBy para WideEntry (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363325"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="1c4a2-102">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-102">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="1c4a2-103">Define os tipos .NET que usam essa definição da exibição larga ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-103">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="1c4a2-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1c4a2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c4a2-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1c4a2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1c4a2-106">Attributes and Elements</span></span>

<span data-ttu-id="1c4a2-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1c4a2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1c4a2-108">Attributes</span></span>

<span data-ttu-id="1c4a2-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1c4a2-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="1c4a2-110">Child Elements</span></span>

|<span data-ttu-id="1c4a2-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c4a2-111">Element</span></span>|<span data-ttu-id="1c4a2-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="1c4a2-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1c4a2-113">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-113">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="1c4a2-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-114">Optional element.</span></span><br /><br /> <span data-ttu-id="1c4a2-115">Define a condição que deve existir para essa definição de exibição ampla ser usada.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-115">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="1c4a2-116">Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-116">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="1c4a2-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="1c4a2-118">Especifica um conjunto de tipos .NET que usam essa definição de exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-118">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="1c4a2-119">Elemento TypeName para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-119">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="1c4a2-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-120">Optional element.</span></span><br /><br /> <span data-ttu-id="1c4a2-121">Especifica um tipo .NET que usa essa definição de exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-121">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1c4a2-122">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="1c4a2-122">Parent Elements</span></span>

|<span data-ttu-id="1c4a2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c4a2-123">Element</span></span>|<span data-ttu-id="1c4a2-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="1c4a2-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1c4a2-125">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="1c4a2-126">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1c4a2-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="1c4a2-127">Remarks</span></span>

<span data-ttu-id="1c4a2-128">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição de exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-128">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="1c4a2-129">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="1c4a2-130">As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade específico ou um valor de script é avaliado como `true`.</span><span class="sxs-lookup"><span data-stu-id="1c4a2-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="1c4a2-131">Para obter mais informações sobre condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1c4a2-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="1c4a2-132">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="1c4a2-132">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c4a2-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c4a2-133">See Also</span></span>

[<span data-ttu-id="1c4a2-134">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-134">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="1c4a2-135">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-135">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="1c4a2-136">Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-136">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="1c4a2-137">Elemento TypeName para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1c4a2-137">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="1c4a2-138">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="1c4a2-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="1c4a2-139">Definindo condições para exibir dados</span><span class="sxs-lookup"><span data-stu-id="1c4a2-139">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1c4a2-140">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c4a2-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
