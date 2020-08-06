---
title: Elemento PropertyName para SelectionCondition para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 251fc129896cfa4a6255330e23854b014675ac5f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780807"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="5c87b-102">Elemento PropertyName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5c87b-102">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="5c87b-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="5c87b-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="5c87b-104">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada é usada.</span><span class="sxs-lookup"><span data-stu-id="5c87b-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="5c87b-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="5c87b-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="5c87b-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para controles para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para o elemento View (Format) PropertyName para SelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5c87b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5c87b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5c87b-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5c87b-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5c87b-108">Attributes and Elements</span></span>

<span data-ttu-id="5c87b-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="5c87b-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5c87b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c87b-110">Attributes</span></span>

<span data-ttu-id="5c87b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5c87b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5c87b-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5c87b-112">Child Elements</span></span>

<span data-ttu-id="5c87b-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5c87b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5c87b-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5c87b-114">Parent Elements</span></span>

|<span data-ttu-id="5c87b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c87b-115">Element</span></span>|<span data-ttu-id="5c87b-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c87b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c87b-117">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5c87b-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="5c87b-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="5c87b-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5c87b-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="5c87b-119">Text Value</span></span>

<span data-ttu-id="5c87b-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="5c87b-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c87b-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="5c87b-121">Remarks</span></span>

<span data-ttu-id="5c87b-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="5c87b-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="5c87b-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="5c87b-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c87b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c87b-124">See Also</span></span>

[<span data-ttu-id="5c87b-125">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5c87b-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="5c87b-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c87b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
