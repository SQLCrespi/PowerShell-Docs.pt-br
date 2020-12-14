---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)
description: Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)
ms.openlocfilehash: bda34b0c1e97fb85536132bedcec3986072801b7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665695"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="ff39c-103">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="ff39c-103">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="ff39c-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="ff39c-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="ff39c-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="ff39c-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="ff39c-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ff39c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff39c-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ff39c-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff39c-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ff39c-108">Attributes and Elements</span></span>

<span data-ttu-id="ff39c-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="ff39c-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff39c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff39c-110">Attributes</span></span>

<span data-ttu-id="ff39c-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ff39c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff39c-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ff39c-112">Child Elements</span></span>

<span data-ttu-id="ff39c-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ff39c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ff39c-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ff39c-114">Parent Elements</span></span>

|<span data-ttu-id="ff39c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff39c-115">Element</span></span>|<span data-ttu-id="ff39c-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff39c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff39c-117">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ff39c-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="ff39c-118">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="ff39c-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ff39c-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="ff39c-119">Text Value</span></span>

<span data-ttu-id="ff39c-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="ff39c-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff39c-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="ff39c-121">Remarks</span></span>

<span data-ttu-id="ff39c-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="ff39c-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="ff39c-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ff39c-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="ff39c-124">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="ff39c-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff39c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff39c-125">See Also</span></span>

[<span data-ttu-id="ff39c-126">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="ff39c-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ff39c-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="ff39c-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ff39c-128">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ff39c-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ff39c-129">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ff39c-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ff39c-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff39c-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
