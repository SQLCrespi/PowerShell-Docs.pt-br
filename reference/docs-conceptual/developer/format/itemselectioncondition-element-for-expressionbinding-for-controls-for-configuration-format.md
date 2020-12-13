---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)
description: Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)
ms.openlocfilehash: 6bd3d386ba64b33a1744fcc9e602cf13404765a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648085"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="aba7e-103">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aba7e-103">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="aba7e-104">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="aba7e-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="aba7e-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="aba7e-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="aba7e-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para o elemento Configuration (Format) ItemSelectionCondition para ExpressionBinding para controles para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aba7e-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aba7e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aba7e-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aba7e-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="aba7e-108">Attributes and Elements</span></span>

<span data-ttu-id="aba7e-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="aba7e-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aba7e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="aba7e-110">Attributes</span></span>

<span data-ttu-id="aba7e-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="aba7e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aba7e-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="aba7e-112">Child Elements</span></span>

|<span data-ttu-id="aba7e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="aba7e-113">Element</span></span>|<span data-ttu-id="aba7e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="aba7e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aba7e-115">Elemento PropertyName para ItemSelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="aba7e-115">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="aba7e-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aba7e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="aba7e-117">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="aba7e-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="aba7e-118">Elemento ScriptBlock para ItemSelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aba7e-118">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="aba7e-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aba7e-119">Optional element.</span></span><br /><br /> <span data-ttu-id="aba7e-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="aba7e-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aba7e-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="aba7e-121">Parent Elements</span></span>

|<span data-ttu-id="aba7e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="aba7e-122">Element</span></span>|<span data-ttu-id="aba7e-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="aba7e-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aba7e-124">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aba7e-124">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="aba7e-125">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="aba7e-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aba7e-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="aba7e-126">Remarks</span></span>

<span data-ttu-id="aba7e-127">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="aba7e-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="aba7e-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aba7e-128">See Also</span></span>

[<span data-ttu-id="aba7e-129">Elemento PropertyName para ItemSelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="aba7e-129">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="aba7e-130">Elemento ScriptBlock para ItemSelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aba7e-130">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="aba7e-131">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aba7e-131">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="aba7e-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="aba7e-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
