---
title: Elemento EntrySelectedBy para CustomEntry para CustomControl para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4d4900cefb0d499397fc9dff7e037ce0a541f72f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783680"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="56aa8-102">Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="56aa8-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="56aa8-103">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="56aa8-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="56aa8-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="56aa8-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="56aa8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="56aa8-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="56aa8-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="56aa8-106">Attributes and Elements</span></span>

<span data-ttu-id="56aa8-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="56aa8-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="56aa8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="56aa8-108">Attributes</span></span>

<span data-ttu-id="56aa8-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="56aa8-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="56aa8-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="56aa8-110">Child Elements</span></span>

|<span data-ttu-id="56aa8-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="56aa8-111">Element</span></span>|<span data-ttu-id="56aa8-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="56aa8-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56aa8-113">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="56aa8-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="56aa8-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="56aa8-114">Optional element.</span></span><br /><br /> <span data-ttu-id="56aa8-115">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="56aa8-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="56aa8-116">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="56aa8-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="56aa8-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="56aa8-117">Optional element.</span></span><br /><br /> <span data-ttu-id="56aa8-118">Especifica um conjunto de tipos .NET que usam essa definição do modo de exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="56aa8-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="56aa8-119">Elemento TypeName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="56aa8-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="56aa8-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="56aa8-120">Optional element.</span></span><br /><br /> <span data-ttu-id="56aa8-121">Especifica um tipo .NET que usa essa definição do modo de exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="56aa8-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="56aa8-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="56aa8-122">Parent Elements</span></span>

|<span data-ttu-id="56aa8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="56aa8-123">Element</span></span>|<span data-ttu-id="56aa8-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="56aa8-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56aa8-125">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="56aa8-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="56aa8-126">Define os controles usados por objetos .NET específicos.</span><span class="sxs-lookup"><span data-stu-id="56aa8-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="56aa8-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="56aa8-127">Remarks</span></span>

<span data-ttu-id="56aa8-128">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="56aa8-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="56aa8-129">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="56aa8-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="56aa8-130">As condições de seleção são usadas para definir uma condição que deve existir para a entrada a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="56aa8-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="56aa8-131">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="56aa8-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="56aa8-132">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [modo de exibição de controle personalizado](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="56aa8-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56aa8-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56aa8-133">See Also</span></span>

[<span data-ttu-id="56aa8-134">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="56aa8-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="56aa8-135">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="56aa8-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="56aa8-136">Elemento TypeName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="56aa8-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="56aa8-137">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="56aa8-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="56aa8-138">Exibição de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="56aa8-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="56aa8-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="56aa8-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
