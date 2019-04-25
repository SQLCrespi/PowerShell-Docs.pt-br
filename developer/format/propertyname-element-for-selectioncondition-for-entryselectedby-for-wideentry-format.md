---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340abb12-6df1-42f4-bdae-b0509c90952c
caps.latest.revision: 11
ms.openlocfilehash: 196877b97db9ed0592e357486c1318dc1e7efd31
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064672"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="2951a-102">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2951a-102">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="2951a-103">Especifica a propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="2951a-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="2951a-104">Quando essa propriedade estiver presente ou quando ela é avaliada como `true`, a condição for atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="2951a-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="2951a-105">Elemento (formato) elemento ViewDefinitions (formato) exibição elemento (formato) elemento WideControl (formato) elemento WideEntries (formato) elemento WideEntry (formato) EntrySelectedBy elemento de configuração para elemento de SelectionCondition WideEntry (formato) EntrySelectedBy para elemento de PropertyName WideEntry (formato) SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2951a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2951a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2951a-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2951a-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="2951a-107">Attributes and Elements</span></span>

<span data-ttu-id="2951a-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="2951a-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2951a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="2951a-109">Attributes</span></span>

<span data-ttu-id="2951a-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2951a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2951a-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2951a-111">Child Elements</span></span>

<span data-ttu-id="2951a-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2951a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2951a-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2951a-113">Parent Elements</span></span>

|<span data-ttu-id="2951a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2951a-114">Element</span></span>|<span data-ttu-id="2951a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2951a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2951a-116">Elemento SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2951a-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="2951a-117">Define a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="2951a-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2951a-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2951a-118">Text Value</span></span>

<span data-ttu-id="2951a-119">Especifique o nome de propriedade do .NET.</span><span class="sxs-lookup"><span data-stu-id="2951a-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="2951a-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="2951a-120">Remarks</span></span>

<span data-ttu-id="2951a-121">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script para avaliar, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="2951a-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="2951a-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2951a-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2951a-123">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="2951a-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2951a-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2951a-124">See Also</span></span>

[<span data-ttu-id="2951a-125">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="2951a-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2951a-126">Definir condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="2951a-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2951a-127">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2951a-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="2951a-128">Elemento SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2951a-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="2951a-129">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2951a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
