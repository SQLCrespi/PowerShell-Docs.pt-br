---
title: Elemento SelectionSetName para EntrySelectedBy para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42143d1e-7cda-4c4a-b568-fa1951bb9417
caps.latest.revision: 6
ms.openlocfilehash: 9060ee54d6f88c7f910b16cf5c9b87f37844b736
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364785"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="26192-102">Elemento SelectionSetName para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="26192-102">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="26192-103">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="26192-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="26192-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="26192-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="26192-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionSetName para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="26192-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="26192-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="26192-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="26192-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="26192-107">Attributes and Elements</span></span>

<span data-ttu-id="26192-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="26192-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="26192-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="26192-109">Attributes</span></span>

<span data-ttu-id="26192-110">Não</span><span class="sxs-lookup"><span data-stu-id="26192-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="26192-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="26192-111">Child Elements</span></span>

<span data-ttu-id="26192-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="26192-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="26192-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="26192-113">Parent Elements</span></span>

|<span data-ttu-id="26192-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="26192-114">Element</span></span>|<span data-ttu-id="26192-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="26192-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26192-116">Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="26192-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="26192-117">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="26192-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="26192-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="26192-118">Text Value</span></span>

<span data-ttu-id="26192-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="26192-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="26192-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="26192-120">Remarks</span></span>

<span data-ttu-id="26192-121">Cada definição de controle deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="26192-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="26192-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="26192-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="26192-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="26192-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26192-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26192-124">See Also</span></span>

[<span data-ttu-id="26192-125">Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="26192-125">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="26192-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="26192-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
