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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368055"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="3c905-102">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3c905-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="3c905-103">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3c905-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="3c905-104">Quando esse tipo está presente, a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="3c905-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="3c905-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy para o elemento TypeName WideEntry (Format) para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3c905-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3c905-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3c905-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3c905-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3c905-107">Attributes and Elements</span></span>

<span data-ttu-id="3c905-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="3c905-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3c905-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c905-109">Attributes</span></span>

<span data-ttu-id="3c905-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3c905-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3c905-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="3c905-111">Child Elements</span></span>

<span data-ttu-id="3c905-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3c905-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3c905-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="3c905-113">Parent Elements</span></span>

|<span data-ttu-id="3c905-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c905-114">Element</span></span>|<span data-ttu-id="3c905-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c905-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3c905-116">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3c905-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="3c905-117">Define a condição que deve existir para que essa entrada ampla seja usada.</span><span class="sxs-lookup"><span data-stu-id="3c905-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3c905-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="3c905-118">Text Value</span></span>

<span data-ttu-id="3c905-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="3c905-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c905-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="3c905-120">Remarks</span></span>

<span data-ttu-id="3c905-121">A condição de seleção pode especificar um tipo .NET ou um conjunto de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="3c905-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="3c905-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="3c905-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="3c905-123">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="3c905-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c905-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3c905-124">See Also</span></span>

[<span data-ttu-id="3c905-125">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="3c905-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="3c905-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="3c905-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="3c905-127">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3c905-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3c905-128">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3c905-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="3c905-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c905-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
