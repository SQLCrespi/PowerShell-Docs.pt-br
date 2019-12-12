---
title: Elemento ScriptBlock para SelectionCondition para CustomControl para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7031fa8b-3e2b-4ea8-89cb-95171f467b5a
caps.latest.revision: 6
ms.openlocfilehash: e55d1c5aa533005b258ecbbbf3ed9d55f852eab6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368635"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="39d6b-102">Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="39d6b-102">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="39d6b-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="39d6b-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="39d6b-104">Quando esse script é avaliado como `true`, a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="39d6b-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="39d6b-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="39d6b-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="39d6b-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl for View ( Format) elemento CustomItem para CustomEntry para CustomControl para o elemento View (Format) SelectionCondition para EntrySelectedBy para CustomControl para o elemento de ScriptBlock View (Format) para SelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="39d6b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="39d6b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="39d6b-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="39d6b-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="39d6b-108">Attributes and Elements</span></span>

<span data-ttu-id="39d6b-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="39d6b-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="39d6b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="39d6b-110">Attributes</span></span>

<span data-ttu-id="39d6b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="39d6b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="39d6b-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="39d6b-112">Child Elements</span></span>

<span data-ttu-id="39d6b-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="39d6b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="39d6b-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="39d6b-114">Parent Elements</span></span>

|<span data-ttu-id="39d6b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="39d6b-115">Element</span></span>|<span data-ttu-id="39d6b-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="39d6b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="39d6b-117">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="39d6b-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="39d6b-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="39d6b-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="39d6b-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="39d6b-119">Text Value</span></span>

<span data-ttu-id="39d6b-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="39d6b-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="39d6b-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="39d6b-121">Remarks</span></span>

<span data-ttu-id="39d6b-122">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="39d6b-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="39d6b-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="39d6b-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39d6b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39d6b-124">See Also</span></span>

[<span data-ttu-id="39d6b-125">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="39d6b-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="39d6b-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="39d6b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
