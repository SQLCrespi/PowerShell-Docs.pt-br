---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3f0a6b6b381f39492da36dab271503fc7cf6e7fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785550"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="507e6-102">Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="507e6-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="507e6-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="507e6-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="507e6-104">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="507e6-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="507e6-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName elemento para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="507e6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="507e6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="507e6-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="507e6-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="507e6-107">Attributes and Elements</span></span>

<span data-ttu-id="507e6-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="507e6-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="507e6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="507e6-109">Attributes</span></span>

<span data-ttu-id="507e6-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="507e6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="507e6-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="507e6-111">Child Elements</span></span>

<span data-ttu-id="507e6-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="507e6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="507e6-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="507e6-113">Parent Elements</span></span>

|<span data-ttu-id="507e6-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="507e6-114">Element</span></span>|<span data-ttu-id="507e6-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="507e6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="507e6-116">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="507e6-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="507e6-117">Define a condição que deve existir para que essa entrada de lista seja usada.</span><span class="sxs-lookup"><span data-stu-id="507e6-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="507e6-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="507e6-118">Text Value</span></span>

<span data-ttu-id="507e6-119">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="507e6-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="507e6-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="507e6-120">Remarks</span></span>

<span data-ttu-id="507e6-121">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="507e6-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="507e6-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="507e6-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="507e6-123">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="507e6-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="507e6-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="507e6-124">See Also</span></span>

[<span data-ttu-id="507e6-125">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="507e6-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="507e6-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="507e6-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="507e6-127">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="507e6-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="507e6-128">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="507e6-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="507e6-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="507e6-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
