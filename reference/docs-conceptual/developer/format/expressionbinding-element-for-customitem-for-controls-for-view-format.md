---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ExpressionBinding para CustomItem para Controls para View (formato)
description: Elemento ExpressionBinding para CustomItem para Controls para View (formato)
ms.openlocfilehash: da87bb26d21dcb051871e67997cc3fba7ce73c74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649899"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="173eb-103">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-103">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="173eb-104">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="173eb-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="173eb-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="173eb-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="173eb-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="173eb-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="173eb-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="173eb-107">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="173eb-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="173eb-108">Attributes and Elements</span></span>

<span data-ttu-id="173eb-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ExpressionBinding` elemento.</span><span class="sxs-lookup"><span data-stu-id="173eb-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="173eb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="173eb-110">Attributes</span></span>

<span data-ttu-id="173eb-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="173eb-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="173eb-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="173eb-112">Child Elements</span></span>

|<span data-ttu-id="173eb-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="173eb-113">Element</span></span>|<span data-ttu-id="173eb-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="173eb-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="173eb-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="173eb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="173eb-116">Define um controle que é usado por este controle.</span><span class="sxs-lookup"><span data-stu-id="173eb-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="173eb-117">Elemento CustomControlName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-117">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="173eb-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="173eb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="173eb-119">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="173eb-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="173eb-120">Elemento EnumerateCollection para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-120">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="173eb-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="173eb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="173eb-122">Especifica que os elementos das coleções são exibidos.</span><span class="sxs-lookup"><span data-stu-id="173eb-122">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="173eb-123">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="173eb-123">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="173eb-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="173eb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="173eb-125">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="173eb-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="173eb-126">Elemento PropertyName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-126">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="173eb-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="173eb-127">Optional element.</span></span><br /><br /> <span data-ttu-id="173eb-128">Especifica a propriedade .NET cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="173eb-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="173eb-129">Elemento ScriptBlock para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-129">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="173eb-130">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="173eb-130">Optional element.</span></span><br /><br /> <span data-ttu-id="173eb-131">Especifica o script cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="173eb-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="173eb-132">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="173eb-132">Parent Elements</span></span>

|<span data-ttu-id="173eb-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="173eb-133">Element</span></span>|<span data-ttu-id="173eb-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="173eb-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="173eb-135">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-135">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="173eb-136">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="173eb-136">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="173eb-137">Comentários</span><span class="sxs-lookup"><span data-stu-id="173eb-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="173eb-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="173eb-138">See Also</span></span>

[<span data-ttu-id="173eb-139">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="173eb-140">Elemento CustomControlName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-140">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="173eb-141">Elemento EnumerateCollection para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-141">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="173eb-142">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="173eb-142">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="173eb-143">Elemento PropertyName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-143">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="173eb-144">Elemento ScriptBlock para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="173eb-144">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="173eb-145">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="173eb-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
