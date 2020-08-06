---
title: Elemento SelectionSetName para SelectionCondition para CustomControl para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c7fdd92475ba24d27e61371d1c6b54fa1a55647c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787505"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="609f4-102">Elemento SelectionSetName para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="609f4-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="609f4-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="609f4-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="609f4-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="609f4-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="609f4-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="609f4-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="609f4-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="609f4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="609f4-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="609f4-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="609f4-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="609f4-108">Attributes and Elements</span></span>

<span data-ttu-id="609f4-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="609f4-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="609f4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="609f4-110">Attributes</span></span>

<span data-ttu-id="609f4-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="609f4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="609f4-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="609f4-112">Child Elements</span></span>

<span data-ttu-id="609f4-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="609f4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="609f4-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="609f4-114">Parent Elements</span></span>

|<span data-ttu-id="609f4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="609f4-115">Element</span></span>|<span data-ttu-id="609f4-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="609f4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="609f4-117">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="609f4-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="609f4-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="609f4-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="609f4-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="609f4-119">Text Value</span></span>

<span data-ttu-id="609f4-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="609f4-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="609f4-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="609f4-121">Remarks</span></span>

<span data-ttu-id="609f4-122">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="609f4-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="609f4-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="609f4-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="609f4-124">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="609f4-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="609f4-125">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="609f4-125">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="609f4-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="609f4-126">See Also</span></span>

[<span data-ttu-id="609f4-127">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="609f4-127">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="609f4-128">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="609f4-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="609f4-129">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="609f4-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="609f4-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="609f4-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
