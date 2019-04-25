---
title: Elemento ExpressionBinding para CustomItem para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065913"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="92e2a-102">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="92e2a-103">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="92e2a-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="92e2a-104">Esse elemento é usado ao definir uma exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="92e2a-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="92e2a-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento CustomControl elemento de configuração para elemento de exibição (formato) CustomEntries CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para CustomControl para exibição ( Elemento de CustomItem Format) para CustomEntry para CustomControl para elemento de exibição (formato) ExpressionBinding CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92e2a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92e2a-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="92e2a-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="92e2a-107">Attributes and Elements</span></span>

<span data-ttu-id="92e2a-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ExpressionBinding` elemento.</span><span class="sxs-lookup"><span data-stu-id="92e2a-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92e2a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="92e2a-109">Attributes</span></span>

<span data-ttu-id="92e2a-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="92e2a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92e2a-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="92e2a-111">Child Elements</span></span>

|<span data-ttu-id="92e2a-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="92e2a-112">Element</span></span>|<span data-ttu-id="92e2a-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="92e2a-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="92e2a-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="92e2a-114">Optional element.</span></span><br /><br /> <span data-ttu-id="92e2a-115">Define um controle que é usado por esse controle.</span><span class="sxs-lookup"><span data-stu-id="92e2a-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="92e2a-116">Elemento CustomControlName para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="92e2a-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="92e2a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="92e2a-118">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="92e2a-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="92e2a-119">Elemento EnumerateCollection para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="92e2a-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="92e2a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="92e2a-121">Especificado que os elementos das coleções são exibidos.</span><span class="sxs-lookup"><span data-stu-id="92e2a-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="92e2a-122">Elemento ItemSelectionCondition para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="92e2a-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="92e2a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="92e2a-124">Define a condição que deve existir para esse controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="92e2a-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="92e2a-125">Elemento PropertyName para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="92e2a-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="92e2a-126">Optional element.</span></span><br /><br /> <span data-ttu-id="92e2a-127">Especifica a propriedade .NET cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="92e2a-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="92e2a-128">Elemento ScriptBlock para ExpressionBinding para CustomCustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="92e2a-129">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="92e2a-129">Optional element.</span></span><br /><br /> <span data-ttu-id="92e2a-130">Especifica o script cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="92e2a-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="92e2a-131">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="92e2a-131">Parent Elements</span></span>

|<span data-ttu-id="92e2a-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="92e2a-132">Element</span></span>|<span data-ttu-id="92e2a-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="92e2a-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92e2a-134">Elemento CustomItem para CustomEntry para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="92e2a-135">Define quais dados são exibidos com o modo de exibição do controle personalizado e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="92e2a-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="92e2a-136">Comentários</span><span class="sxs-lookup"><span data-stu-id="92e2a-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="92e2a-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92e2a-137">See Also</span></span>

[<span data-ttu-id="92e2a-138">Elemento CustomControlName para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="92e2a-139">Elemento EnumerateCollection para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="92e2a-140">Elemento ItemSelectionCondition para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="92e2a-141">Elemento PropertyName para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="92e2a-142">Elemento ScriptBlock para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="92e2a-143">Elemento CustomItem para CustomEntry para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="92e2a-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="92e2a-144">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="92e2a-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
