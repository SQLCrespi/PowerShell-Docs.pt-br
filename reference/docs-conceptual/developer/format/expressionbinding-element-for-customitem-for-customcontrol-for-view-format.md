---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)
description: Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648186"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="5f337-103">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-103">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="5f337-104">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="5f337-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="5f337-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="5f337-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="5f337-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl para o elemento View (Format) CustomItem para CustomEntry para CustomControl para o elemento ExpressionBinding de exibição (Format) para CustomItem para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5f337-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5f337-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5f337-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="5f337-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5f337-108">Attributes and Elements</span></span>

<span data-ttu-id="5f337-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ExpressionBinding` elemento.</span><span class="sxs-lookup"><span data-stu-id="5f337-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f337-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5f337-110">Attributes</span></span>

<span data-ttu-id="5f337-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="5f337-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f337-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5f337-112">Child Elements</span></span>

|<span data-ttu-id="5f337-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f337-113">Element</span></span>|<span data-ttu-id="5f337-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f337-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="5f337-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5f337-115">Optional element.</span></span><br /><br /> <span data-ttu-id="5f337-116">Define um controle que é usado por este controle.</span><span class="sxs-lookup"><span data-stu-id="5f337-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="5f337-117">Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-117">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="5f337-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5f337-118">Optional element.</span></span><br /><br /> <span data-ttu-id="5f337-119">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="5f337-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="5f337-120">Elemento EnumerateCollection para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-120">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="5f337-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5f337-121">Optional element.</span></span><br /><br /> <span data-ttu-id="5f337-122">Especificado que os elementos das coleções são exibidos.</span><span class="sxs-lookup"><span data-stu-id="5f337-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="5f337-123">Elemento ItemSelectionCondition para ExpressionBinding para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5f337-123">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="5f337-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5f337-124">Optional element.</span></span><br /><br /> <span data-ttu-id="5f337-125">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="5f337-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="5f337-126">Elemento PropertyName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-126">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="5f337-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5f337-127">Optional element.</span></span><br /><br /> <span data-ttu-id="5f337-128">Especifica a propriedade .NET cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="5f337-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="5f337-129">Elemento ScriptBlock para ExpressionBinding para CustomCustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5f337-129">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="5f337-130">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5f337-130">Optional element.</span></span><br /><br /> <span data-ttu-id="5f337-131">Especifica o script cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="5f337-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5f337-132">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5f337-132">Parent Elements</span></span>

|<span data-ttu-id="5f337-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f337-133">Element</span></span>|<span data-ttu-id="5f337-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f337-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f337-135">Elemento CustomItem para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-135">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="5f337-136">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="5f337-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5f337-137">Comentários</span><span class="sxs-lookup"><span data-stu-id="5f337-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="5f337-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5f337-138">See Also</span></span>

[<span data-ttu-id="5f337-139">Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-139">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5f337-140">Elemento EnumerateCollection para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-140">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5f337-141">Elemento ItemSelectionCondition para ExpressionBinding para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="5f337-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="5f337-142">Elemento PropertyName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-142">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5f337-143">Elemento ScriptBlock para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-143">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5f337-144">Elemento CustomItem para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5f337-144">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5f337-145">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f337-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
