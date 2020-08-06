---
title: Elemento ScriptBlock para SelectionCondition para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e5f4295a989307cb6ffb655c2c39596f3d1ea806
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785414"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="4c685-102">Elemento ScriptBlock para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="4c685-102">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="4c685-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="4c685-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="4c685-104">Quando esse script é avaliado como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="4c685-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="4c685-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="4c685-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="4c685-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para controles para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para View (Format) elemento ScriptBlock para SelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4c685-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4c685-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4c685-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4c685-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4c685-108">Attributes and Elements</span></span>

<span data-ttu-id="4c685-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="4c685-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4c685-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4c685-110">Attributes</span></span>

<span data-ttu-id="4c685-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4c685-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4c685-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="4c685-112">Child Elements</span></span>

<span data-ttu-id="4c685-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4c685-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4c685-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="4c685-114">Parent Elements</span></span>

|<span data-ttu-id="4c685-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c685-115">Element</span></span>|<span data-ttu-id="4c685-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c685-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c685-117">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="4c685-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="4c685-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="4c685-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4c685-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="4c685-119">Text Value</span></span>

<span data-ttu-id="4c685-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="4c685-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c685-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="4c685-121">Remarks</span></span>

<span data-ttu-id="4c685-122">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="4c685-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="4c685-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4c685-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c685-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c685-124">See Also</span></span>

[<span data-ttu-id="4c685-125">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="4c685-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="4c685-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c685-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
