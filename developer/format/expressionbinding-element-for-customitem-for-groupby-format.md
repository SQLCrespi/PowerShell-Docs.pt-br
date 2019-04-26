---
title: Elemento ExpressionBinding para CustomItem para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065896"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="d534e-102">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="d534e-103">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="d534e-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="d534e-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="d534e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d534e-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) CustomItem CustomEntry para elemento de GroupBy (formato) ExpressionBinding CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d534e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d534e-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d534e-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="d534e-107">Attributes and Elements</span></span>

<span data-ttu-id="d534e-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ExpressionBinding` elemento.</span><span class="sxs-lookup"><span data-stu-id="d534e-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d534e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d534e-109">Attributes</span></span>

<span data-ttu-id="d534e-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d534e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d534e-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d534e-111">Child Elements</span></span>

|<span data-ttu-id="d534e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="d534e-112">Element</span></span>|<span data-ttu-id="d534e-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="d534e-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="d534e-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d534e-114">Optional element.</span></span><br /><br /> <span data-ttu-id="d534e-115">Define um controle que é usado por esse controle.</span><span class="sxs-lookup"><span data-stu-id="d534e-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="d534e-116">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d534e-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d534e-117">Optional element.</span></span><br /><br /> <span data-ttu-id="d534e-118">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="d534e-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="d534e-119">[Elemento EnumerateCollection para ExpressionBinding para GroupBy (formato)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)elemento EnumerateCollection para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="d534e-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d534e-120">Optional element.</span></span><br /><br /> <span data-ttu-id="d534e-121">Especificado que os elementos das coleções são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d534e-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="d534e-122">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d534e-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d534e-123">Optional element.</span></span><br /><br /> <span data-ttu-id="d534e-124">Define a condição que deve existir para esse controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="d534e-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="d534e-125">Elemento PropertyName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d534e-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d534e-126">Optional element.</span></span><br /><br /> <span data-ttu-id="d534e-127">Especifica a propriedade .NET cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="d534e-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="d534e-128">Elemento ScriptBlock para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d534e-129">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d534e-129">Optional element.</span></span><br /><br /> <span data-ttu-id="d534e-130">Especifica o script cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="d534e-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d534e-131">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d534e-131">Parent Elements</span></span>

|<span data-ttu-id="d534e-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="d534e-132">Element</span></span>|<span data-ttu-id="d534e-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="d534e-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d534e-134">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="d534e-135">Define quais dados são exibidos com o modo de exibição do controle personalizado e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="d534e-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d534e-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d534e-136">See Also</span></span>

[<span data-ttu-id="d534e-137">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d534e-138">Elemento EnumerateCollection para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d534e-139">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d534e-140">Elemento PropertyName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d534e-141">Elemento ScriptBlock para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d534e-142">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d534e-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="d534e-143">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d534e-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
