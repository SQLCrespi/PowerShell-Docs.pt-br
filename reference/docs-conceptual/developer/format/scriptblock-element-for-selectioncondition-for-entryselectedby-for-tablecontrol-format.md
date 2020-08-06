---
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a23d3515749393e9f5a2053634a44d1a817ebf38
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783442"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="f7ba2-102">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f7ba2-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="f7ba2-103">Especifica o bloco de script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-103">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="f7ba2-104">Quando esse script é avaliado como `true` , a condição é atendida e a entrada da tabela é usada.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-104">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="f7ba2-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element para EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f7ba2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f7ba2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f7ba2-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7ba2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f7ba2-107">Attributes and Elements</span></span>

<span data-ttu-id="f7ba2-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7ba2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f7ba2-109">Attributes</span></span>

<span data-ttu-id="f7ba2-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f7ba2-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f7ba2-111">Child Elements</span></span>

<span data-ttu-id="f7ba2-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7ba2-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f7ba2-113">Parent Elements</span></span>

|<span data-ttu-id="f7ba2-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7ba2-114">Element</span></span>|<span data-ttu-id="f7ba2-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7ba2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f7ba2-116">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f7ba2-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f7ba2-117">Define a condição que deve existir para que essa entrada de tabela seja usada.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f7ba2-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f7ba2-118">Text Value</span></span>

<span data-ttu-id="f7ba2-119">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7ba2-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="f7ba2-120">Remarks</span></span>

<span data-ttu-id="f7ba2-121">A condição de seleção deve especificar pelo menos um bloco de script ou nome de propriedade, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="f7ba2-121">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="f7ba2-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f7ba2-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f7ba2-123">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f7ba2-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7ba2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7ba2-124">See Also</span></span>

[<span data-ttu-id="f7ba2-125">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="f7ba2-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f7ba2-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="f7ba2-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f7ba2-127">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="f7ba2-127">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="f7ba2-128">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f7ba2-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f7ba2-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7ba2-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
