---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)
description: Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)
ms.openlocfilehash: adbe747bdb4f6c1d180e5b630247de0fd3d72b85
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648059"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="cc8b8-103">Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-103">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="cc8b8-104">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="cc8b8-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="cc8b8-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento viewbinding de exibição (Format) para CustomItem para controles para o elemento View (Format) ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc8b8-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc8b8-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc8b8-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="cc8b8-108">Attributes and Elements</span></span>

<span data-ttu-id="cc8b8-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc8b8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc8b8-110">Attributes</span></span>

<span data-ttu-id="cc8b8-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc8b8-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="cc8b8-112">Child Elements</span></span>

|<span data-ttu-id="cc8b8-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc8b8-113">Element</span></span>|<span data-ttu-id="cc8b8-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc8b8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc8b8-115">Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-115">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="cc8b8-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-116">Optional element.</span></span><br /><br /> <span data-ttu-id="cc8b8-117">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="cc8b8-118">Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-118">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="cc8b8-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-119">Optional element.</span></span><br /><br /> <span data-ttu-id="cc8b8-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cc8b8-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="cc8b8-121">Parent Elements</span></span>

|<span data-ttu-id="cc8b8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc8b8-122">Element</span></span>|<span data-ttu-id="cc8b8-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc8b8-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc8b8-124">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-124">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="cc8b8-125">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cc8b8-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="cc8b8-126">Remarks</span></span>

<span data-ttu-id="cc8b8-127">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc8b8-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc8b8-128">See Also</span></span>

[<span data-ttu-id="cc8b8-129">Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-129">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="cc8b8-130">Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-130">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="cc8b8-131">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc8b8-131">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="cc8b8-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc8b8-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
