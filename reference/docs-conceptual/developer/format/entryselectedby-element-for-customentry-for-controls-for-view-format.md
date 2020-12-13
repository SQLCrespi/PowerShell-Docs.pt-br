---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)
description: Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)
ms.openlocfilehash: 29b0574a95d81962fb3f72a526f89273baeea647
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660260"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="65a2c-103">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="65a2c-103">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="65a2c-104">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="65a2c-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="65a2c-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="65a2c-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="65a2c-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para os controles do elemento View (Format) EntrySelectedBy para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="65a2c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65a2c-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="65a2c-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="65a2c-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="65a2c-108">Attributes and Elements</span></span>

<span data-ttu-id="65a2c-109">As seções a seguir descrevem atributos, elementos filho e elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="65a2c-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="65a2c-110">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição.</span><span class="sxs-lookup"><span data-stu-id="65a2c-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="65a2c-111">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="65a2c-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="65a2c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="65a2c-112">Attributes</span></span>

<span data-ttu-id="65a2c-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="65a2c-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65a2c-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="65a2c-114">Child Elements</span></span>

|<span data-ttu-id="65a2c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a2c-115">Element</span></span>|<span data-ttu-id="65a2c-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="65a2c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65a2c-117">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="65a2c-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="65a2c-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="65a2c-118">Optional element.</span></span><br /><br /> <span data-ttu-id="65a2c-119">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="65a2c-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="65a2c-120">Elemento SelectionSetName para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="65a2c-120">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="65a2c-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="65a2c-121">Optional element.</span></span><br /><br /> <span data-ttu-id="65a2c-122">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="65a2c-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="65a2c-123">Elemento TypeName para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="65a2c-123">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="65a2c-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="65a2c-124">Optional element.</span></span><br /><br /> <span data-ttu-id="65a2c-125">Especifica um tipo .NET que usa essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="65a2c-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="65a2c-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="65a2c-126">Parent Elements</span></span>

|<span data-ttu-id="65a2c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a2c-127">Element</span></span>|<span data-ttu-id="65a2c-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="65a2c-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65a2c-129">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="65a2c-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="65a2c-130">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="65a2c-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="65a2c-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="65a2c-131">Remarks</span></span>

<span data-ttu-id="65a2c-132">As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="65a2c-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="65a2c-133">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="65a2c-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65a2c-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65a2c-134">See Also</span></span>

[<span data-ttu-id="65a2c-135">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="65a2c-135">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="65a2c-136">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a2c-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
