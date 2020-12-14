---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)
description: Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)
ms.openlocfilehash: dcb59fc438ae217870566f09204fb16b8f031614
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665780"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="827a1-103">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="827a1-103">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="827a1-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="827a1-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="827a1-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada da tabela é usada.</span><span class="sxs-lookup"><span data-stu-id="827a1-105">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="827a1-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element para EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="827a1-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="827a1-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="827a1-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="827a1-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="827a1-108">Attributes and Elements</span></span>

<span data-ttu-id="827a1-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="827a1-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="827a1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="827a1-110">Attributes</span></span>

<span data-ttu-id="827a1-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="827a1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="827a1-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="827a1-112">Child Elements</span></span>

<span data-ttu-id="827a1-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="827a1-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="827a1-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="827a1-114">Parent Elements</span></span>

|<span data-ttu-id="827a1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="827a1-115">Element</span></span>|<span data-ttu-id="827a1-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="827a1-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="827a1-117">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="827a1-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="827a1-118">Define a condição que deve existir para que essa entrada de tabela seja usada.</span><span class="sxs-lookup"><span data-stu-id="827a1-118">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="827a1-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="827a1-119">Text Value</span></span>

<span data-ttu-id="827a1-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="827a1-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="827a1-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="827a1-121">Remarks</span></span>

<span data-ttu-id="827a1-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="827a1-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="827a1-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="827a1-123">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="827a1-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="827a1-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="827a1-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="827a1-125">See Also</span></span>

[<span data-ttu-id="827a1-126">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="827a1-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="827a1-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="827a1-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="827a1-128">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="827a1-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="827a1-129">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="827a1-129">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="827a1-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="827a1-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
