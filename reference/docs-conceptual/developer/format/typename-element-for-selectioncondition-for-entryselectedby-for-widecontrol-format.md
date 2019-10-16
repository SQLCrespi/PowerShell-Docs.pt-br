---
title: Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d6d43fa-c900-4e2f-952d-deccd584236f
caps.latest.revision: 11
ms.openlocfilehash: 6142350e3843a5feddcb5cee8901bbfa607d8d4c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368055"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="54604-102">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="54604-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="54604-103">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="54604-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="54604-104">Quando esse tipo está presente, a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="54604-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="54604-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy para o elemento TypeName WideEntry (Format) para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="54604-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="54604-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="54604-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="54604-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="54604-107">Attributes and Elements</span></span>

<span data-ttu-id="54604-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="54604-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="54604-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="54604-109">Attributes</span></span>

<span data-ttu-id="54604-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="54604-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="54604-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="54604-111">Child Elements</span></span>

<span data-ttu-id="54604-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="54604-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="54604-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="54604-113">Parent Elements</span></span>

|<span data-ttu-id="54604-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="54604-114">Element</span></span>|<span data-ttu-id="54604-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="54604-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="54604-116">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="54604-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="54604-117">Define a condição que deve existir para que essa entrada ampla seja usada.</span><span class="sxs-lookup"><span data-stu-id="54604-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="54604-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="54604-118">Text Value</span></span>

<span data-ttu-id="54604-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="54604-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="54604-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="54604-120">Remarks</span></span>

<span data-ttu-id="54604-121">A condição de seleção pode especificar um tipo .NET ou um conjunto de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="54604-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="54604-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="54604-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="54604-123">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="54604-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54604-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54604-124">See Also</span></span>

[<span data-ttu-id="54604-125">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="54604-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="54604-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="54604-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="54604-127">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="54604-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="54604-128">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="54604-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="54604-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="54604-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
