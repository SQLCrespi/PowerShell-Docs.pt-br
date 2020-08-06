---
title: Elemento SelectionSetName para EntrySelectedBy para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 546225b0619ebec83d04a7e27bbc298ffef0a14d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785244"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="35916-102">Elemento SelectionSetName para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="35916-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="35916-103">Especifica um conjunto de objetos .NET para a definição.</span><span class="sxs-lookup"><span data-stu-id="35916-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="35916-104">A definição é usada sempre que um desses objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="35916-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="35916-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35916-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="35916-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="35916-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="35916-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="35916-107">Attributes and Elements</span></span>

<span data-ttu-id="35916-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="35916-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="35916-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="35916-109">Attributes</span></span>

<span data-ttu-id="35916-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="35916-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="35916-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="35916-111">Child Elements</span></span>

<span data-ttu-id="35916-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="35916-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="35916-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="35916-113">Parent Elements</span></span>

|<span data-ttu-id="35916-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="35916-114">Element</span></span>|<span data-ttu-id="35916-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="35916-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35916-116">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="35916-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="35916-117">Define os tipos .NET que usam essa entrada ampla ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="35916-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="35916-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="35916-118">Text Value</span></span>

<span data-ttu-id="35916-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="35916-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="35916-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="35916-120">Remarks</span></span>

<span data-ttu-id="35916-121">Cada definição deve especificar um nome de tipo, um conjunto de seleção ou uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="35916-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="35916-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="35916-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="35916-123">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="35916-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="35916-124">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="35916-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="35916-125">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="35916-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35916-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35916-126">See Also</span></span>

[<span data-ttu-id="35916-127">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="35916-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="35916-128">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="35916-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="35916-129">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="35916-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="35916-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="35916-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
