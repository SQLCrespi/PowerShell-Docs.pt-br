---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)
description: Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)
ms.openlocfilehash: 42e9d2b00f7690e46242b2c4602245e4bf391bbf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664954"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="b8f5e-103">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="b8f5e-103">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b8f5e-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="b8f5e-105">Quando esse script é avaliado como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="b8f5e-106">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b8f5e-107">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para controles para o elemento ScriptBlock de configuração (Format) para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="b8f5e-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b8f5e-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b8f5e-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b8f5e-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b8f5e-109">Attributes and Elements</span></span>

<span data-ttu-id="b8f5e-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b8f5e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b8f5e-111">Attributes</span></span>

<span data-ttu-id="b8f5e-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b8f5e-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b8f5e-113">Child Elements</span></span>

<span data-ttu-id="b8f5e-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b8f5e-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b8f5e-115">Parent Elements</span></span>

|<span data-ttu-id="b8f5e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8f5e-116">Element</span></span>|<span data-ttu-id="b8f5e-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8f5e-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b8f5e-118">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="b8f5e-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="b8f5e-119">Define uma condição que deve existir para que a definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-119">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b8f5e-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b8f5e-120">Text Value</span></span>

<span data-ttu-id="b8f5e-121">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8f5e-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="b8f5e-122">Remarks</span></span>

<span data-ttu-id="b8f5e-123">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="b8f5e-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="b8f5e-124">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b8f5e-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8f5e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b8f5e-125">See Also</span></span>

[<span data-ttu-id="b8f5e-126">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="b8f5e-126">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="b8f5e-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8f5e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
