---
title: Elemento SelectionSetName para EntrySelectedBy para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 362f7844c09a52494387a62e329adfb309767427
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785278"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="21b61-102">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="21b61-102">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="21b61-103">Especifica um conjunto de objetos .NET para a entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="21b61-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="21b61-104">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="21b61-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="21b61-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="21b61-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="21b61-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element for CustomEntry para o elemento SelectionSetName GroupBy (Format) para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="21b61-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="21b61-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="21b61-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="21b61-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="21b61-108">Attributes and Elements</span></span>

<span data-ttu-id="21b61-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="21b61-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="21b61-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="21b61-110">Attributes</span></span>

<span data-ttu-id="21b61-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="21b61-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="21b61-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="21b61-112">Child Elements</span></span>

<span data-ttu-id="21b61-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="21b61-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="21b61-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="21b61-114">Parent Elements</span></span>

|<span data-ttu-id="21b61-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="21b61-115">Element</span></span>|<span data-ttu-id="21b61-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="21b61-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21b61-117">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="21b61-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="21b61-118">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="21b61-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="21b61-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="21b61-119">Text Value</span></span>

<span data-ttu-id="21b61-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="21b61-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="21b61-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="21b61-121">Remarks</span></span>

<span data-ttu-id="21b61-122">Cada definição de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="21b61-122">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="21b61-123">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="21b61-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="21b61-124">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="21b61-124">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="21b61-125">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="21b61-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="21b61-126">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="21b61-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21b61-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="21b61-127">See Also</span></span>

[<span data-ttu-id="21b61-128">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="21b61-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="21b61-129">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="21b61-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="21b61-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="21b61-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
