---
title: Elemento SelectionSetName para EntrySelectedBy para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5c762a626fff746266919d1f7fcb991a8cdbcdf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787539"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="ab081-102">Elemento SelectionSetName para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ab081-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="ab081-103">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="ab081-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="ab081-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="ab081-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ab081-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionSetName para EntrySelectedBy para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="ab081-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ab081-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ab081-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ab081-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ab081-107">Attributes and Elements</span></span>

<span data-ttu-id="ab081-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="ab081-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab081-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ab081-109">Attributes</span></span>

<span data-ttu-id="ab081-110">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ab081-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="ab081-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ab081-111">Child Elements</span></span>

<span data-ttu-id="ab081-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ab081-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ab081-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ab081-113">Parent Elements</span></span>

|<span data-ttu-id="ab081-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab081-114">Element</span></span>|<span data-ttu-id="ab081-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab081-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab081-116">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ab081-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="ab081-117">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="ab081-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ab081-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="ab081-118">Text Value</span></span>

<span data-ttu-id="ab081-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="ab081-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab081-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="ab081-120">Remarks</span></span>

<span data-ttu-id="ab081-121">Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="ab081-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="ab081-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="ab081-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="ab081-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ab081-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab081-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab081-124">See Also</span></span>

[<span data-ttu-id="ab081-125">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ab081-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="ab081-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab081-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
