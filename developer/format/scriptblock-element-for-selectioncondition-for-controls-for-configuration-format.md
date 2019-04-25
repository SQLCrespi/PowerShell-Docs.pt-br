---
title: Elemento ScriptBlock para SelectionCondition para controles de configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb032dfc-9ef6-403c-b557-5858617e3483
caps.latest.revision: 6
ms.openlocfilehash: 102987970152420896a0c986f0973280ae209623
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064417"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="70cdf-102">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="70cdf-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="70cdf-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="70cdf-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="70cdf-104">Quando esse script é avaliado para `true`, a condição for atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="70cdf-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="70cdf-105">Esse elemento é usado durante a definição de um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="70cdf-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="70cdf-106">Elemento de controles de (formato) do elemento de configuração do elemento de controle de configuração (formato) para controles para o elemento de CustomControl de configuração (formato) para o controle para o elemento de configuração (formato) de CustomEntries para CustomControl para configuração ( Elemento de CustomEntry Format) para CustomControl controles para o elemento de configuração (formato) de EntrySelectedBy para CustomEntry controles para o elemento de configuração (formato) de SelectionCondition para EntrySelectedBy para controles de configuração (formato) Elemento ScriptBlock para SelectionCondition para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="70cdf-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="70cdf-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="70cdf-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="70cdf-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="70cdf-108">Attributes and Elements</span></span>

<span data-ttu-id="70cdf-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="70cdf-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="70cdf-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="70cdf-110">Attributes</span></span>

<span data-ttu-id="70cdf-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="70cdf-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="70cdf-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="70cdf-112">Child Elements</span></span>

<span data-ttu-id="70cdf-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="70cdf-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="70cdf-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="70cdf-114">Parent Elements</span></span>

|<span data-ttu-id="70cdf-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="70cdf-115">Element</span></span>|<span data-ttu-id="70cdf-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="70cdf-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70cdf-117">Elemento SelectionCondition para EntrySelectedBy para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="70cdf-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="70cdf-118">Define uma condição que deve existir para a definição de controle comum a ser usado.</span><span class="sxs-lookup"><span data-stu-id="70cdf-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="70cdf-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="70cdf-119">Text Value</span></span>

<span data-ttu-id="70cdf-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="70cdf-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="70cdf-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="70cdf-121">Remarks</span></span>

<span data-ttu-id="70cdf-122">A condição de seleção deve especificar pelo menos um script ou a propriedade nome para avaliar, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="70cdf-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="70cdf-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="70cdf-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="70cdf-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70cdf-124">See Also</span></span>

[<span data-ttu-id="70cdf-125">Elemento SelectionCondition para EntrySelectedBy para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="70cdf-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="70cdf-126">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="70cdf-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
