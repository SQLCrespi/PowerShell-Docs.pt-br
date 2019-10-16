---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340abb12-6df1-42f4-bdae-b0509c90952c
caps.latest.revision: 11
ms.openlocfilehash: 196877b97db9ed0592e357486c1318dc1e7efd31
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362235"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="23409-102">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="23409-102">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="23409-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="23409-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="23409-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="23409-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="23409-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy para WideEntry (Format) PropertyName elemento para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="23409-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="23409-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="23409-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="23409-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="23409-107">Attributes and Elements</span></span>

<span data-ttu-id="23409-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="23409-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="23409-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="23409-109">Attributes</span></span>

<span data-ttu-id="23409-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="23409-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="23409-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="23409-111">Child Elements</span></span>

<span data-ttu-id="23409-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="23409-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="23409-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="23409-113">Parent Elements</span></span>

|<span data-ttu-id="23409-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="23409-114">Element</span></span>|<span data-ttu-id="23409-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="23409-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="23409-116">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="23409-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="23409-117">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="23409-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="23409-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="23409-118">Text Value</span></span>

<span data-ttu-id="23409-119">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="23409-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="23409-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="23409-120">Remarks</span></span>

<span data-ttu-id="23409-121">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="23409-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="23409-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="23409-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="23409-123">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="23409-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="23409-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23409-124">See Also</span></span>

[<span data-ttu-id="23409-125">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="23409-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="23409-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="23409-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="23409-127">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="23409-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="23409-128">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="23409-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="23409-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="23409-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
