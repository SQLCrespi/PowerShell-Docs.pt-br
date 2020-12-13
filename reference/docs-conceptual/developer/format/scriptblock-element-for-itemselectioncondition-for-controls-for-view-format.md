---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)
description: Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)
ms.openlocfilehash: c005215f7b7984541806d2f5de47372d536787ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665188"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="7e28f-103">Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7e28f-103">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="7e28f-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="7e28f-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="7e28f-105">Quando esse script é avaliado como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="7e28f-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="7e28f-106">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="7e28f-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="7e28f-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para o elemento View (Format) ItemSelectionCondition de ExpressionBinding para controles para View (Format) elemento ScriptBlock para ItemSelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7e28f-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7e28f-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7e28f-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7e28f-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7e28f-109">Attributes and Elements</span></span>

<span data-ttu-id="7e28f-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="7e28f-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7e28f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7e28f-111">Attributes</span></span>

<span data-ttu-id="7e28f-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7e28f-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7e28f-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="7e28f-113">Child Elements</span></span>

<span data-ttu-id="7e28f-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7e28f-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7e28f-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="7e28f-115">Parent Elements</span></span>

|<span data-ttu-id="7e28f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e28f-116">Element</span></span>|<span data-ttu-id="7e28f-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="7e28f-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7e28f-118">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7e28f-118">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="7e28f-119">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="7e28f-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7e28f-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="7e28f-120">Text Value</span></span>

<span data-ttu-id="7e28f-121">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="7e28f-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e28f-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="7e28f-122">Remarks</span></span>

<span data-ttu-id="7e28f-123">Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="7e28f-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e28f-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e28f-124">See Also</span></span>

[<span data-ttu-id="7e28f-125">Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7e28f-125">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="7e28f-126">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7e28f-126">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="7e28f-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e28f-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
