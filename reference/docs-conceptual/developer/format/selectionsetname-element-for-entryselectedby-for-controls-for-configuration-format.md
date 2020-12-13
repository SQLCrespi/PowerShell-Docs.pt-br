---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)
description: Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)
ms.openlocfilehash: b775aa8a3184aa3ebcbda17a8e3191c69d67a700
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645732"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="91a7e-103">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="91a7e-103">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="91a7e-104">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="91a7e-104">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="91a7e-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="91a7e-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="91a7e-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionSetName para EntrySelectedBy para controles para</span><span class="sxs-lookup"><span data-stu-id="91a7e-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91a7e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91a7e-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="91a7e-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="91a7e-108">Attributes and Elements</span></span>

<span data-ttu-id="91a7e-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="91a7e-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91a7e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="91a7e-110">Attributes</span></span>

<span data-ttu-id="91a7e-111">Nenhum</span><span class="sxs-lookup"><span data-stu-id="91a7e-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="91a7e-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="91a7e-112">Child Elements</span></span>

<span data-ttu-id="91a7e-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="91a7e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91a7e-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="91a7e-114">Parent Elements</span></span>

|<span data-ttu-id="91a7e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="91a7e-115">Element</span></span>|<span data-ttu-id="91a7e-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="91a7e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91a7e-117">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="91a7e-117">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="91a7e-118">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="91a7e-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="91a7e-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="91a7e-119">Text Value</span></span>

<span data-ttu-id="91a7e-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="91a7e-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="91a7e-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="91a7e-121">Remarks</span></span>

<span data-ttu-id="91a7e-122">Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="91a7e-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="91a7e-123">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="91a7e-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="91a7e-124">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="91a7e-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="91a7e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91a7e-125">See Also</span></span>

[<span data-ttu-id="91a7e-126">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="91a7e-126">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="91a7e-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="91a7e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
