---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)
description: Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)
ms.openlocfilehash: 1abcf2173e18d45839161b4c7e59f1ad238f81a1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655334"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="e8f5b-103">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e8f5b-103">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e8f5b-104">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="e8f5b-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e8f5b-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para os controles do elemento ExpressionBinding de configuração para CustomItem para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="e8f5b-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8f5b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8f5b-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e8f5b-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e8f5b-108">Attributes and Elements</span></span>

<span data-ttu-id="e8f5b-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ExpressionBinding` elemento.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8f5b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8f5b-110">Attributes</span></span>

<span data-ttu-id="e8f5b-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8f5b-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e8f5b-112">Child Elements</span></span>

|<span data-ttu-id="e8f5b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8f5b-113">Element</span></span>|<span data-ttu-id="e8f5b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8f5b-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="e8f5b-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e8f5b-116">Define um controle que é usado por este controle.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="e8f5b-117">Elemento CustomControlName para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e8f5b-117">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="e8f5b-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e8f5b-119">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="e8f5b-120">Elemento EnumerateCollection para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e8f5b-120">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="e8f5b-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e8f5b-122">Especificado que os elementos das coleções são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-122">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="e8f5b-123">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e8f5b-123">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="e8f5b-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e8f5b-125">Define a condição que deve existir para que esse controle comum seja usado.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-125">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="e8f5b-126">Elemento PropertyName para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e8f5b-126">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="e8f5b-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-127">Optional element.</span></span><br /><br /> <span data-ttu-id="e8f5b-128">Especifica a propriedade .NET cujo valor é exibido pelo controle comum.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-128">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="e8f5b-129">Elemento ScriptBlock para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e8f5b-129">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="e8f5b-130">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-130">Optional element.</span></span><br /><br /> <span data-ttu-id="e8f5b-131">Especifica o script cujo valor é exibido pelo controle comum.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-131">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e8f5b-132">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e8f5b-132">Parent Elements</span></span>

|<span data-ttu-id="e8f5b-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8f5b-133">Element</span></span>|<span data-ttu-id="e8f5b-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8f5b-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8f5b-135">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="e8f5b-135">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="e8f5b-136">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="e8f5b-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e8f5b-137">Comentários</span><span class="sxs-lookup"><span data-stu-id="e8f5b-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e8f5b-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8f5b-138">See Also</span></span>

[<span data-ttu-id="e8f5b-139">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="e8f5b-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="e8f5b-140">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8f5b-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
