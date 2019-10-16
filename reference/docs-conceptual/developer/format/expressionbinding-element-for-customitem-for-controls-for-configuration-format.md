---
title: Elemento ExpressionBinding para CustomItem para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363185"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="45dff-102">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="45dff-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="45dff-103">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="45dff-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="45dff-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="45dff-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="45dff-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="45dff-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45dff-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45dff-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="45dff-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="45dff-107">Attributes and Elements</span></span>

<span data-ttu-id="45dff-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ExpressionBinding`.</span><span class="sxs-lookup"><span data-stu-id="45dff-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="45dff-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="45dff-109">Attributes</span></span>

<span data-ttu-id="45dff-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="45dff-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45dff-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="45dff-111">Child Elements</span></span>

|<span data-ttu-id="45dff-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="45dff-112">Element</span></span>|<span data-ttu-id="45dff-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="45dff-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="45dff-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="45dff-114">Optional element.</span></span><br /><br /> <span data-ttu-id="45dff-115">Define um controle que é usado por este controle.</span><span class="sxs-lookup"><span data-stu-id="45dff-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="45dff-116">Elemento CustomControlName para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="45dff-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="45dff-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="45dff-117">Optional element.</span></span><br /><br /> <span data-ttu-id="45dff-118">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="45dff-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="45dff-119">Elemento enumeracollection para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="45dff-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="45dff-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="45dff-120">Optional element.</span></span><br /><br /> <span data-ttu-id="45dff-121">Especificado que os elementos das coleções são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="45dff-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="45dff-122">Elemento ItemSelectionCondition para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="45dff-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="45dff-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="45dff-123">Optional element.</span></span><br /><br /> <span data-ttu-id="45dff-124">Define a condição que deve existir para que esse controle comum seja usado.</span><span class="sxs-lookup"><span data-stu-id="45dff-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="45dff-125">Elemento PropertyName para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="45dff-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="45dff-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="45dff-126">Optional element.</span></span><br /><br /> <span data-ttu-id="45dff-127">Especifica a propriedade .NET cujo valor é exibido pelo controle comum.</span><span class="sxs-lookup"><span data-stu-id="45dff-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="45dff-128">Elemento ScriptBlock para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="45dff-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="45dff-129">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="45dff-129">Optional element.</span></span><br /><br /> <span data-ttu-id="45dff-130">Especifica o script cujo valor é exibido pelo controle comum.</span><span class="sxs-lookup"><span data-stu-id="45dff-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="45dff-131">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="45dff-131">Parent Elements</span></span>

|<span data-ttu-id="45dff-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="45dff-132">Element</span></span>|<span data-ttu-id="45dff-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="45dff-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45dff-134">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="45dff-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="45dff-135">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="45dff-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45dff-136">Comentários</span><span class="sxs-lookup"><span data-stu-id="45dff-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="45dff-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45dff-137">See Also</span></span>

[<span data-ttu-id="45dff-138">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="45dff-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="45dff-139">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="45dff-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
