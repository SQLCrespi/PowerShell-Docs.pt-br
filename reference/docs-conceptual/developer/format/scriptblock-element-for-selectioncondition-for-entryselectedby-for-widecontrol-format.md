---
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8f2223d4a1217786a930eb82390c24b81d2f72e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787607"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="0ce06-102">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="0ce06-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="0ce06-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0ce06-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="0ce06-104">Quando esse script é avaliado como `true` , a condição é atendida e a definição de entrada larga é usada.</span><span class="sxs-lookup"><span data-stu-id="0ce06-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="0ce06-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0ce06-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0ce06-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0ce06-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0ce06-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0ce06-107">Attributes and Elements</span></span>

<span data-ttu-id="0ce06-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="0ce06-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0ce06-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0ce06-109">Attributes</span></span>

<span data-ttu-id="0ce06-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0ce06-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0ce06-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0ce06-111">Child Elements</span></span>

<span data-ttu-id="0ce06-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0ce06-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0ce06-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0ce06-113">Parent Elements</span></span>

|<span data-ttu-id="0ce06-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ce06-114">Element</span></span>|<span data-ttu-id="0ce06-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="0ce06-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0ce06-116">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0ce06-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="0ce06-117">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="0ce06-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0ce06-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0ce06-118">Text Value</span></span>

<span data-ttu-id="0ce06-119">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="0ce06-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ce06-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="0ce06-120">Remarks</span></span>

<span data-ttu-id="0ce06-121">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="0ce06-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="0ce06-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0ce06-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="0ce06-123">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="0ce06-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ce06-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ce06-124">See Also</span></span>

[<span data-ttu-id="0ce06-125">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="0ce06-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0ce06-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="0ce06-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0ce06-127">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="0ce06-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="0ce06-128">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0ce06-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="0ce06-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ce06-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
