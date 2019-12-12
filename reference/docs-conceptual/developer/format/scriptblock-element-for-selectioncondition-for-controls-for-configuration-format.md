---
title: Elemento ScriptBlock para SelectionCondition para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb032dfc-9ef6-403c-b557-5858617e3483
caps.latest.revision: 6
ms.openlocfilehash: 102987970152420896a0c986f0973280ae209623
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368615"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="28060-102">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="28060-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="28060-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="28060-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="28060-104">Quando esse script é avaliado como `true`, a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="28060-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="28060-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="28060-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="28060-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para controles para configuração (Format) Elemento ScriptBlock para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="28060-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="28060-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="28060-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28060-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="28060-108">Attributes and Elements</span></span>

<span data-ttu-id="28060-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="28060-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="28060-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="28060-110">Attributes</span></span>

<span data-ttu-id="28060-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="28060-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28060-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="28060-112">Child Elements</span></span>

<span data-ttu-id="28060-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="28060-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="28060-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="28060-114">Parent Elements</span></span>

|<span data-ttu-id="28060-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="28060-115">Element</span></span>|<span data-ttu-id="28060-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="28060-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28060-117">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="28060-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="28060-118">Define uma condição que deve existir para que a definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="28060-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="28060-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="28060-119">Text Value</span></span>

<span data-ttu-id="28060-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="28060-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="28060-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="28060-121">Remarks</span></span>

<span data-ttu-id="28060-122">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="28060-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="28060-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="28060-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="28060-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28060-124">See Also</span></span>

[<span data-ttu-id="28060-125">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="28060-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="28060-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="28060-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
