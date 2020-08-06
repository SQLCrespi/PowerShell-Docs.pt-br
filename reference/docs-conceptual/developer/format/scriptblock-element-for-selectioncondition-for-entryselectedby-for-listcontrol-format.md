---
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 56bd04c9af74bdaa7a186a208fc15a67cb08b004
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772851"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="ca063-102">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="ca063-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="ca063-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="ca063-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="ca063-104">Quando esse script é avaliado como `true` , a condição é atendida e a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="ca063-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="ca063-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) ListControl Element (Format) o elemento ListEntries (Format) ListEntry Element (Format) o elemento EntrySelectedBy para SelectionCondition para EntrySelectedBy (Format) ListEntry Element for SelectionCondition for EntrySelectedBy (Format) o elemento do ScriptBlock para ListEntry para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ca063-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ca063-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ca063-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ca063-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ca063-107">Attributes and Elements</span></span>

<span data-ttu-id="ca063-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="ca063-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ca063-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca063-109">Attributes</span></span>

<span data-ttu-id="ca063-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ca063-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ca063-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ca063-111">Child Elements</span></span>

<span data-ttu-id="ca063-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ca063-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ca063-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ca063-113">Parent Elements</span></span>

|<span data-ttu-id="ca063-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca063-114">Element</span></span>|<span data-ttu-id="ca063-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="ca063-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca063-116">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ca063-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="ca063-117">Define a condição que deve existir para que essa entrada de lista seja usada.</span><span class="sxs-lookup"><span data-stu-id="ca063-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ca063-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="ca063-118">Text Value</span></span>

<span data-ttu-id="ca063-119">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="ca063-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca063-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="ca063-120">Remarks</span></span>

<span data-ttu-id="ca063-121">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="ca063-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="ca063-122">(Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando uma entrada ou item de exibição é usado](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="ca063-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="ca063-123">Para obter mais informações sobre os outros componentes de um modo de exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ca063-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca063-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca063-124">See Also</span></span>

[<span data-ttu-id="ca063-125">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ca063-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="ca063-126">Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ca063-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="ca063-127">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ca063-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="ca063-128">Exibição de lista</span><span class="sxs-lookup"><span data-stu-id="ca063-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ca063-129">Definindo condições para quando uma entrada ou item de exibição é usado</span><span class="sxs-lookup"><span data-stu-id="ca063-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ca063-130">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca063-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
