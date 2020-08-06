---
title: Elemento SelectionSetName para EntrySelectedBy para CustomControl para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3728a1886d5406b8fa4888125d1c031d0f9b1b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785295"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="1e94e-102">Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="1e94e-102">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="1e94e-103">Especifica um conjunto de objetos .NET para a entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="1e94e-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="1e94e-104">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="1e94e-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="1e94e-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para o elemento View (Format) SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1e94e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1e94e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1e94e-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e94e-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1e94e-107">Attributes and Elements</span></span>

<span data-ttu-id="1e94e-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="1e94e-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e94e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e94e-109">Attributes</span></span>

<span data-ttu-id="1e94e-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1e94e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e94e-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1e94e-111">Child Elements</span></span>

<span data-ttu-id="1e94e-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1e94e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1e94e-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1e94e-113">Parent Elements</span></span>

|<span data-ttu-id="1e94e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e94e-114">Element</span></span>|<span data-ttu-id="1e94e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e94e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e94e-116">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e94e-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="1e94e-117">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="1e94e-117">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1e94e-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1e94e-118">Text Value</span></span>

<span data-ttu-id="1e94e-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="1e94e-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e94e-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="1e94e-120">Remarks</span></span>

<span data-ttu-id="1e94e-121">Cada entrada de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="1e94e-121">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="1e94e-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="1e94e-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="1e94e-123">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="1e94e-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="1e94e-124">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1e94e-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="1e94e-125">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="1e94e-125">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e94e-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e94e-126">See Also</span></span>

[<span data-ttu-id="1e94e-127">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e94e-127">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="1e94e-128">Exibição de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="1e94e-128">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="1e94e-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e94e-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
