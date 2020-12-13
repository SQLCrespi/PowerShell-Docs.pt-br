---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ExpressionBinding para CustomItem para GroupBy (formato)
description: Elemento ExpressionBinding para CustomItem para GroupBy (formato)
ms.openlocfilehash: 742d9f081a674dc3ee4c84d600933aaf57b2aa6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655306"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="2fe3d-103">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-103">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="2fe3d-104">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="2fe3d-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2fe3d-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento de GroupBy (Format) CustomEntry para CustomControl para o elemento de CustomItem GroupBy (Format) para CustomEntry para o elemento ExpressionBinding GroupBy (Format) para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2fe3d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2fe3d-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="2fe3d-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2fe3d-108">Attributes and Elements</span></span>

<span data-ttu-id="2fe3d-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ExpressionBinding` elemento.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2fe3d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2fe3d-110">Attributes</span></span>

<span data-ttu-id="2fe3d-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2fe3d-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2fe3d-112">Child Elements</span></span>

|<span data-ttu-id="2fe3d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2fe3d-113">Element</span></span>|<span data-ttu-id="2fe3d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="2fe3d-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="2fe3d-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-115">Optional element.</span></span><br /><br /> <span data-ttu-id="2fe3d-116">Define um controle que é usado por este controle.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="2fe3d-117">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-117">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="2fe3d-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-118">Optional element.</span></span><br /><br /> <span data-ttu-id="2fe3d-119">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-119">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="2fe3d-120">[Elemento enumeracollection para ExpressionBinding para GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Elemento enumeracollection para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-120">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="2fe3d-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="2fe3d-122">Especificado que os elementos das coleções são exibidos.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="2fe3d-123">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-123">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="2fe3d-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-124">Optional element.</span></span><br /><br /> <span data-ttu-id="2fe3d-125">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="2fe3d-126">Elemento PropertyName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-126">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="2fe3d-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-127">Optional element.</span></span><br /><br /> <span data-ttu-id="2fe3d-128">Especifica a propriedade .NET cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="2fe3d-129">Elemento ScriptBlock para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-129">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="2fe3d-130">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-130">Optional element.</span></span><br /><br /> <span data-ttu-id="2fe3d-131">Especifica o script cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2fe3d-132">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2fe3d-132">Parent Elements</span></span>

|<span data-ttu-id="2fe3d-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="2fe3d-133">Element</span></span>|<span data-ttu-id="2fe3d-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="2fe3d-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2fe3d-135">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-135">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="2fe3d-136">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="2fe3d-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2fe3d-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fe3d-137">See Also</span></span>

[<span data-ttu-id="2fe3d-138">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-138">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="2fe3d-139">Elemento EnumerateCollection para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-139">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="2fe3d-140">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-140">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="2fe3d-141">Elemento PropertyName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-141">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="2fe3d-142">Elemento ScriptBlock para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-142">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="2fe3d-143">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="2fe3d-143">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="2fe3d-144">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fe3d-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
