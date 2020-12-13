---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)
description: Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)
ms.openlocfilehash: 92120ace5ed316fbfbf1d51422071c27d5a604cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651983"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="3f34d-103">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="3f34d-103">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="3f34d-104">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="3f34d-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="3f34d-105">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle.</span><span class="sxs-lookup"><span data-stu-id="3f34d-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="3f34d-106">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="3f34d-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="3f34d-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento de GroupBy (Format) CustomEntry para CustomControl para o elemento de CustomItem GroupBy (Format) para CustomEntry para o elemento ExpressionBinding de GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3f34d-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3f34d-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3f34d-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3f34d-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3f34d-109">Attributes and Elements</span></span>

<span data-ttu-id="3f34d-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="3f34d-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3f34d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3f34d-111">Attributes</span></span>

<span data-ttu-id="3f34d-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="3f34d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3f34d-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="3f34d-113">Child Elements</span></span>

|<span data-ttu-id="3f34d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f34d-114">Element</span></span>|<span data-ttu-id="3f34d-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f34d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f34d-116">Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="3f34d-116">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="3f34d-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3f34d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="3f34d-118">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3f34d-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="3f34d-119">Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="3f34d-119">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="3f34d-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3f34d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="3f34d-121">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3f34d-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3f34d-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="3f34d-122">Parent Elements</span></span>

|<span data-ttu-id="3f34d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f34d-123">Element</span></span>|<span data-ttu-id="3f34d-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f34d-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f34d-125">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="3f34d-125">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="3f34d-126">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="3f34d-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3f34d-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="3f34d-127">Remarks</span></span>

<span data-ttu-id="3f34d-128">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="3f34d-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f34d-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3f34d-129">See Also</span></span>

[<span data-ttu-id="3f34d-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f34d-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="3f34d-131">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="3f34d-131">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
