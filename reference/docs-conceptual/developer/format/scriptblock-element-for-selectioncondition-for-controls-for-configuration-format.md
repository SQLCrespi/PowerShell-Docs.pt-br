---
title: Elemento ScriptBlock para SelectionCondition para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 24584aacd7869abd3dcfc6ff546e6dea4c2c04fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785431"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="be103-102">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="be103-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="be103-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="be103-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="be103-104">Quando esse script é avaliado como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="be103-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="be103-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="be103-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="be103-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para controles para o elemento ScriptBlock de configuração (Format) para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="be103-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="be103-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="be103-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="be103-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="be103-108">Attributes and Elements</span></span>

<span data-ttu-id="be103-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="be103-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="be103-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="be103-110">Attributes</span></span>

<span data-ttu-id="be103-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="be103-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="be103-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="be103-112">Child Elements</span></span>

<span data-ttu-id="be103-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="be103-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="be103-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="be103-114">Parent Elements</span></span>

|<span data-ttu-id="be103-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="be103-115">Element</span></span>|<span data-ttu-id="be103-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="be103-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="be103-117">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="be103-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="be103-118">Define uma condição que deve existir para que a definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="be103-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="be103-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="be103-119">Text Value</span></span>

<span data-ttu-id="be103-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="be103-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="be103-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="be103-121">Remarks</span></span>

<span data-ttu-id="be103-122">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="be103-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="be103-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="be103-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="be103-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="be103-124">See Also</span></span>

[<span data-ttu-id="be103-125">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="be103-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="be103-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="be103-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
