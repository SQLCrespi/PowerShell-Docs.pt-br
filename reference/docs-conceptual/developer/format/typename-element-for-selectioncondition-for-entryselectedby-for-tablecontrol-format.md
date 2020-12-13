---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para SelectionCondition para EntrySelectedBy para TableControl (formato)
description: Elemento TypeName para SelectionCondition para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: 66e90ab33775cf35d5e98e45266996d2d1a622d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659635"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="1486d-103">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="1486d-103">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="1486d-104">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1486d-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="1486d-105">Quando esse tipo está presente, a condição é atendida e a linha da tabela é usada.</span><span class="sxs-lookup"><span data-stu-id="1486d-105">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="1486d-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element para EntrySelectedBy para TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1486d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1486d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1486d-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1486d-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1486d-108">Attributes and Elements</span></span>

<span data-ttu-id="1486d-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="1486d-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1486d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1486d-110">Attributes</span></span>

<span data-ttu-id="1486d-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="1486d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1486d-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1486d-112">Child Elements</span></span>

<span data-ttu-id="1486d-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="1486d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1486d-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1486d-114">Parent Elements</span></span>

|<span data-ttu-id="1486d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="1486d-115">Element</span></span>|<span data-ttu-id="1486d-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="1486d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1486d-117">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1486d-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="1486d-118">Define a condição que deve existir para esta linha de tabela ser usada.</span><span class="sxs-lookup"><span data-stu-id="1486d-118">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1486d-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1486d-119">Text Value</span></span>

<span data-ttu-id="1486d-120">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="1486d-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1486d-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="1486d-121">Remarks</span></span>

<span data-ttu-id="1486d-122">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="1486d-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="1486d-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1486d-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="1486d-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="1486d-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1486d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1486d-125">See Also</span></span>

[<span data-ttu-id="1486d-126">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="1486d-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="1486d-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="1486d-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1486d-128">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1486d-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="1486d-129">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1486d-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="1486d-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1486d-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
