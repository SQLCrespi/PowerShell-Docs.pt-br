---
title: Elemento ExpressionBinding para CustomItem para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363775"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="4612d-102">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="4612d-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="4612d-103">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="4612d-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="4612d-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="4612d-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="4612d-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4612d-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4612d-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="4612d-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4612d-107">Attributes and Elements</span></span>

<span data-ttu-id="4612d-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ExpressionBinding`.</span><span class="sxs-lookup"><span data-stu-id="4612d-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4612d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4612d-109">Attributes</span></span>

<span data-ttu-id="4612d-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4612d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4612d-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="4612d-111">Child Elements</span></span>

|<span data-ttu-id="4612d-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4612d-112">Element</span></span>|<span data-ttu-id="4612d-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="4612d-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="4612d-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4612d-114">Optional element.</span></span><br /><br /> <span data-ttu-id="4612d-115">Define um controle que é usado por este controle.</span><span class="sxs-lookup"><span data-stu-id="4612d-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="4612d-116">Elemento CustomControlName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4612d-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4612d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4612d-118">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="4612d-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="4612d-119">Elemento enumeracollection para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4612d-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4612d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4612d-121">Especifica que os elementos das coleções são exibidos.</span><span class="sxs-lookup"><span data-stu-id="4612d-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="4612d-122">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4612d-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4612d-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4612d-124">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="4612d-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="4612d-125">Elemento PropertyName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4612d-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4612d-126">Optional element.</span></span><br /><br /> <span data-ttu-id="4612d-127">Especifica a propriedade .NET cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="4612d-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="4612d-128">Elemento ScriptBlock para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4612d-129">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4612d-129">Optional element.</span></span><br /><br /> <span data-ttu-id="4612d-130">Especifica o script cujo valor é exibido pelo controle.</span><span class="sxs-lookup"><span data-stu-id="4612d-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4612d-131">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="4612d-131">Parent Elements</span></span>

|<span data-ttu-id="4612d-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="4612d-132">Element</span></span>|<span data-ttu-id="4612d-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="4612d-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4612d-134">Elemento CustomItem para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="4612d-135">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="4612d-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4612d-136">Comentários</span><span class="sxs-lookup"><span data-stu-id="4612d-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="4612d-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4612d-137">See Also</span></span>

[<span data-ttu-id="4612d-138">Elemento CustomItem para CustomEntry para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="4612d-139">Elemento CustomControlName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4612d-140">Elemento enumeracollection para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4612d-141">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4612d-142">Elemento PropertyName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4612d-143">Elemento ScriptBlock para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="4612d-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4612d-144">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4612d-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
