---
title: Elemento EntrySelectedBy para CustomEntry para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 75a0f42e7722b54791a873200a35c8fcbbd665b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774126"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="4a9e0-102">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="4a9e0-103">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="4a9e0-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="4a9e0-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy elemento para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4a9e0-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4a9e0-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4a9e0-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4a9e0-107">Attributes and Elements</span></span>

<span data-ttu-id="4a9e0-108">As seções a seguir descrevem atributos, elementos filho e elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="4a9e0-109">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="4a9e0-110">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="4a9e0-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4a9e0-111">Attributes</span></span>

<span data-ttu-id="4a9e0-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4a9e0-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="4a9e0-113">Child Elements</span></span>

|<span data-ttu-id="4a9e0-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a9e0-114">Element</span></span>|<span data-ttu-id="4a9e0-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="4a9e0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4a9e0-116">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="4a9e0-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4a9e0-118">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="4a9e0-119">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="4a9e0-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4a9e0-121">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="4a9e0-122">Elemento TypeName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="4a9e0-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4a9e0-124">Especifica um tipo .NET que usa essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4a9e0-125">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="4a9e0-125">Parent Elements</span></span>

|<span data-ttu-id="4a9e0-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a9e0-126">Element</span></span>|<span data-ttu-id="4a9e0-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="4a9e0-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4a9e0-128">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="4a9e0-129">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="4a9e0-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4a9e0-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="4a9e0-130">Remarks</span></span>

<span data-ttu-id="4a9e0-131">As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="4a9e0-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="4a9e0-132">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4a9e0-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a9e0-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a9e0-133">See Also</span></span>

[<span data-ttu-id="4a9e0-134">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="4a9e0-135">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="4a9e0-136">Elemento TypeName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="4a9e0-137">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="4a9e0-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="4a9e0-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a9e0-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
