---
title: Elemento SelectionSetName para EntrySelectedBy para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b594a064-746f-4900-99e4-7be7bf5aa5a2
caps.latest.revision: 7
ms.openlocfilehash: d540c99707f4e0796b2d408f2161a9208257ab32
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368345"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="0078e-102">Elemento SelectionSetName para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0078e-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="0078e-103">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="0078e-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="0078e-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0078e-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="0078e-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionSetName para EntrySelectedBy para controles para View ( Ao</span><span class="sxs-lookup"><span data-stu-id="0078e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0078e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0078e-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="0078e-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0078e-107">Attributes and Elements</span></span>

<span data-ttu-id="0078e-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="0078e-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0078e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0078e-109">Attributes</span></span>

<span data-ttu-id="0078e-110">Não</span><span class="sxs-lookup"><span data-stu-id="0078e-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="0078e-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="0078e-111">Child Elements</span></span>

<span data-ttu-id="0078e-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0078e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0078e-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="0078e-113">Parent Elements</span></span>

|<span data-ttu-id="0078e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="0078e-114">Element</span></span>|<span data-ttu-id="0078e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="0078e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0078e-116">Elemento EntrySelectedBy para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="0078e-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="0078e-117">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="0078e-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0078e-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0078e-118">Text Value</span></span>

<span data-ttu-id="0078e-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="0078e-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0078e-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="0078e-120">Remarks</span></span>

<span data-ttu-id="0078e-121">Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="0078e-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="0078e-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="0078e-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="0078e-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0078e-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0078e-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0078e-124">See Also</span></span>

[<span data-ttu-id="0078e-125">Elemento EntrySelectedBy para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="0078e-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="0078e-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0078e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
