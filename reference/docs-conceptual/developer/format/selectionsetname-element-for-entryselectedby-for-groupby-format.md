---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)
description: Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)
ms.openlocfilehash: 7ebe5d884061243c8b4af196788187d84c15a92e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651847"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="68878-103">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="68878-103">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="68878-104">Especifica um conjunto de objetos .NET para a entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="68878-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="68878-105">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="68878-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="68878-106">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="68878-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="68878-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element for CustomEntry para o elemento SelectionSetName GroupBy (Format) para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="68878-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="68878-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68878-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="68878-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="68878-109">Attributes and Elements</span></span>

<span data-ttu-id="68878-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="68878-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="68878-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="68878-111">Attributes</span></span>

<span data-ttu-id="68878-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="68878-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="68878-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="68878-113">Child Elements</span></span>

<span data-ttu-id="68878-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="68878-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="68878-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="68878-115">Parent Elements</span></span>

|<span data-ttu-id="68878-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="68878-116">Element</span></span>|<span data-ttu-id="68878-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="68878-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="68878-118">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="68878-118">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="68878-119">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="68878-119">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="68878-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="68878-120">Text Value</span></span>

<span data-ttu-id="68878-121">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="68878-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="68878-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="68878-122">Remarks</span></span>

<span data-ttu-id="68878-123">Cada definição de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="68878-123">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="68878-124">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="68878-124">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="68878-125">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="68878-125">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="68878-126">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="68878-126">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="68878-127">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="68878-127">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68878-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68878-128">See Also</span></span>

[<span data-ttu-id="68878-129">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="68878-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="68878-130">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="68878-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="68878-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="68878-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
