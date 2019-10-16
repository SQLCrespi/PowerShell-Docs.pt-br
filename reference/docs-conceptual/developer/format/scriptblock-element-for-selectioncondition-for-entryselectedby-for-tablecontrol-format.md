---
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b11fbcf-3426-48ae-9319-2c847969f723
caps.latest.revision: 10
ms.openlocfilehash: 7afc834e68ef332bee1e23da782fb5c5527fcf54
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368575"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="3aad9-102">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3aad9-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="3aad9-103">Especifica o bloco de script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3aad9-103">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="3aad9-104">Quando esse script é avaliado como `true`, a condição é atendida e a entrada da tabela é usada.</span><span class="sxs-lookup"><span data-stu-id="3aad9-104">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="3aad9-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element for TableRowEntry (Format) Elemento SelectionCondition para EntrySelectedBy para o elemento ScriptBlock TableRowEntry (Format) para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3aad9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3aad9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3aad9-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3aad9-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3aad9-107">Attributes and Elements</span></span>

<span data-ttu-id="3aad9-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="3aad9-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3aad9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3aad9-109">Attributes</span></span>

<span data-ttu-id="3aad9-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3aad9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3aad9-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="3aad9-111">Child Elements</span></span>

<span data-ttu-id="3aad9-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3aad9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3aad9-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="3aad9-113">Parent Elements</span></span>

|<span data-ttu-id="3aad9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3aad9-114">Element</span></span>|<span data-ttu-id="3aad9-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="3aad9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3aad9-116">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3aad9-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="3aad9-117">Define a condição que deve existir para que essa entrada de tabela seja usada.</span><span class="sxs-lookup"><span data-stu-id="3aad9-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3aad9-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="3aad9-118">Text Value</span></span>

<span data-ttu-id="3aad9-119">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="3aad9-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="3aad9-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="3aad9-120">Remarks</span></span>

<span data-ttu-id="3aad9-121">A condição de seleção deve especificar pelo menos um bloco de script ou nome de propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="3aad9-121">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="3aad9-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="3aad9-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="3aad9-123">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="3aad9-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3aad9-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3aad9-124">See Also</span></span>

[<span data-ttu-id="3aad9-125">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="3aad9-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3aad9-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="3aad9-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="3aad9-127">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3aad9-127">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="3aad9-128">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3aad9-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="3aad9-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3aad9-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
