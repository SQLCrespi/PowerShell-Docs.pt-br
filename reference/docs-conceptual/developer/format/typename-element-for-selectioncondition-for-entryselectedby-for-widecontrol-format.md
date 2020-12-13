---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (formato)
description: Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (formato)
ms.openlocfilehash: af6e4782c345b43e16bce59c333bdaaceba0d845
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645514"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="bee35-103">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bee35-103">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="bee35-104">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bee35-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="bee35-105">Quando esse tipo está presente, a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="bee35-105">When this type is present, the definition is used.</span></span>

<span data-ttu-id="bee35-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy para WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bee35-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bee35-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bee35-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bee35-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bee35-108">Attributes and Elements</span></span>

<span data-ttu-id="bee35-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="bee35-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bee35-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="bee35-110">Attributes</span></span>

<span data-ttu-id="bee35-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bee35-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bee35-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bee35-112">Child Elements</span></span>

<span data-ttu-id="bee35-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bee35-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bee35-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bee35-114">Parent Elements</span></span>

|<span data-ttu-id="bee35-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="bee35-115">Element</span></span>|<span data-ttu-id="bee35-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="bee35-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bee35-117">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bee35-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="bee35-118">Define a condição que deve existir para que essa entrada ampla seja usada.</span><span class="sxs-lookup"><span data-stu-id="bee35-118">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bee35-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="bee35-119">Text Value</span></span>

<span data-ttu-id="bee35-120">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="bee35-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bee35-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="bee35-121">Remarks</span></span>

<span data-ttu-id="bee35-122">A condição de seleção pode especificar um tipo .NET ou um conjunto de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="bee35-122">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="bee35-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bee35-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bee35-124">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="bee35-124">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bee35-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bee35-125">See Also</span></span>

[<span data-ttu-id="bee35-126">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="bee35-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="bee35-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="bee35-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="bee35-128">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bee35-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="bee35-129">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="bee35-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="bee35-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bee35-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
