---
title: Elemento ScriptBlock para SelectionCondition para CustomControl para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d3506188d32ce85ad6345dc0d0866dd789a1f293
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785397"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="02264-102">Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="02264-102">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="02264-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="02264-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="02264-104">Quando esse script é avaliado como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="02264-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="02264-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="02264-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="02264-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl para o elemento View (Format) CustomItem para CustomEntry para CustomControl para o elemento View (Format) SelectionCondition para EntrySelectedBy para CustomControl para View (Format) elementar para SelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="02264-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="02264-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="02264-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02264-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="02264-108">Attributes and Elements</span></span>

<span data-ttu-id="02264-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="02264-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="02264-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="02264-110">Attributes</span></span>

<span data-ttu-id="02264-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="02264-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="02264-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="02264-112">Child Elements</span></span>

<span data-ttu-id="02264-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="02264-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="02264-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="02264-114">Parent Elements</span></span>

|<span data-ttu-id="02264-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="02264-115">Element</span></span>|<span data-ttu-id="02264-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="02264-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02264-117">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="02264-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="02264-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="02264-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="02264-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="02264-119">Text Value</span></span>

<span data-ttu-id="02264-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="02264-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="02264-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="02264-121">Remarks</span></span>

<span data-ttu-id="02264-122">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="02264-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="02264-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="02264-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02264-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02264-124">See Also</span></span>

[<span data-ttu-id="02264-125">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="02264-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="02264-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="02264-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
