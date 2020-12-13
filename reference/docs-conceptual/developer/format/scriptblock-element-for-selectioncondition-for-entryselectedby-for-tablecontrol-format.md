---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableControl (formato)
description: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: a984bda6b8fba3a5cb9485576ffd847f0d366d3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659895"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b7a14-103">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b7a14-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b7a14-104">Especifica o bloco de script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="b7a14-104">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="b7a14-105">Quando esse script é avaliado como `true` , a condição é atendida e a entrada da tabela é usada.</span><span class="sxs-lookup"><span data-stu-id="b7a14-105">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="b7a14-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element para EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="b7a14-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b7a14-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b7a14-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b7a14-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b7a14-108">Attributes and Elements</span></span>

<span data-ttu-id="b7a14-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="b7a14-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b7a14-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7a14-110">Attributes</span></span>

<span data-ttu-id="b7a14-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b7a14-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b7a14-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b7a14-112">Child Elements</span></span>

<span data-ttu-id="b7a14-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b7a14-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b7a14-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b7a14-114">Parent Elements</span></span>

|<span data-ttu-id="b7a14-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7a14-115">Element</span></span>|<span data-ttu-id="b7a14-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="b7a14-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b7a14-117">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="b7a14-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="b7a14-118">Define a condição que deve existir para que essa entrada de tabela seja usada.</span><span class="sxs-lookup"><span data-stu-id="b7a14-118">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b7a14-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b7a14-119">Text Value</span></span>

<span data-ttu-id="b7a14-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="b7a14-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7a14-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="b7a14-121">Remarks</span></span>

<span data-ttu-id="b7a14-122">A condição de seleção deve especificar pelo menos um bloco de script ou nome de propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="b7a14-122">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="b7a14-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b7a14-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="b7a14-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b7a14-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b7a14-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7a14-125">See Also</span></span>

[<span data-ttu-id="b7a14-126">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="b7a14-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b7a14-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="b7a14-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b7a14-128">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="b7a14-128">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="b7a14-129">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="b7a14-129">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b7a14-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7a14-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
