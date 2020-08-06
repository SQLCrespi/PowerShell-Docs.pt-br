---
title: Elemento SelectionSetName para EntrySelectedBy para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 72072d8d13e6ca22afdb9bca2e0237d29ba0594f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787556"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="dd1f8-102">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="dd1f8-102">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="dd1f8-103">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="dd1f8-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="dd1f8-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionSetName para EntrySelectedBy para controles para</span><span class="sxs-lookup"><span data-stu-id="dd1f8-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dd1f8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd1f8-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="dd1f8-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="dd1f8-107">Attributes and Elements</span></span>

<span data-ttu-id="dd1f8-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dd1f8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="dd1f8-109">Attributes</span></span>

<span data-ttu-id="dd1f8-110">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dd1f8-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="dd1f8-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="dd1f8-111">Child Elements</span></span>

<span data-ttu-id="dd1f8-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dd1f8-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="dd1f8-113">Parent Elements</span></span>

|<span data-ttu-id="dd1f8-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd1f8-114">Element</span></span>|<span data-ttu-id="dd1f8-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd1f8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dd1f8-116">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="dd1f8-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="dd1f8-117">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dd1f8-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="dd1f8-118">Text Value</span></span>

<span data-ttu-id="dd1f8-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd1f8-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd1f8-120">Remarks</span></span>

<span data-ttu-id="dd1f8-121">Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="dd1f8-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="dd1f8-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="dd1f8-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="dd1f8-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd1f8-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd1f8-124">See Also</span></span>

[<span data-ttu-id="dd1f8-125">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="dd1f8-125">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="dd1f8-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd1f8-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
