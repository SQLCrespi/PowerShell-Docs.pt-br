---
title: Elemento ExpressionBinding para CustomItem para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368625"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="13e73-102">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="13e73-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="13e73-103">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="13e73-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="13e73-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="13e73-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="13e73-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) CustomItem elemento para CustomEntry para o elemento ExpressionBinding GroupBy (Format) para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="13e73-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="13e73-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="13e73-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="13e73-107">Attributes and Elements</span></span>

<span data-ttu-id="13e73-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ExpressionBinding`.</span><span class="sxs-lookup"><span data-stu-id="13e73-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="13e73-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="13e73-109">Attributes</span></span>

<span data-ttu-id="13e73-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="13e73-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="13e73-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="13e73-111">Child Elements</span></span>

|<span data-ttu-id="13e73-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="13e73-112">Element</span></span>|<span data-ttu-id="13e73-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="13e73-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="13e73-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="13e73-114">Optional element.</span></span><br /><br /> <span data-ttu-id="13e73-115">Define um controle que é usado por este controle.</span><span class="sxs-lookup"><span data-stu-id="13e73-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="13e73-116">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="13e73-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="13e73-117">Optional element.</span></span><br /><br /> <span data-ttu-id="13e73-118">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="13e73-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="13e73-119">[Elemento enumeracollection para ExpressionBinding para GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Elemento enumeracollection para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="13e73-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="13e73-120">Optional element.</span></span><br /><br /> <span data-ttu-id="13e73-121">Especificado que os elementos das coleções são exibidos.</span><span class="sxs-lookup"><span data-stu-id="13e73-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="13e73-122">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="13e73-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="13e73-123">Optional element.</span></span><br /><br /> <span data-ttu-id="13e73-124">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="13e73-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="13e73-125">Elemento PropertyName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="13e73-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="13e73-126">Optional element.</span></span><br /><br /> <span data-ttu-id="13e73-127">Especifica a propriedade .NET cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="13e73-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="13e73-128">Elemento ScriptBlock para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="13e73-129">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="13e73-129">Optional element.</span></span><br /><br /> <span data-ttu-id="13e73-130">Especifica o script cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="13e73-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="13e73-131">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="13e73-131">Parent Elements</span></span>

|<span data-ttu-id="13e73-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="13e73-132">Element</span></span>|<span data-ttu-id="13e73-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="13e73-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13e73-134">Elemento CustomItem para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="13e73-135">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="13e73-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="13e73-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="13e73-136">See Also</span></span>

[<span data-ttu-id="13e73-137">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="13e73-138">Elemento enumeracollection para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="13e73-139">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="13e73-140">Elemento PropertyName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="13e73-141">Elemento ScriptBlock para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="13e73-142">Elemento CustomItem para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e73-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="13e73-143">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="13e73-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
