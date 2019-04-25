---
title: Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065454"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="ffb2d-102">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ffb2d-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="ffb2d-103">Define a condição que deve existir para esse controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="ffb2d-104">Não há nenhum limite para o número de condições de seleção que pode ser especificado para um item de controle.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="ffb2d-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ffb2d-106">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) CustomItem CustomEntry para elemento de GroupBy (formato) ExpressionBinding CustomItem para elemento de GroupBy (formato) ItemSelectionCondition ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ffb2d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ffb2d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ffb2d-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ffb2d-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="ffb2d-108">Attributes and Elements</span></span>

<span data-ttu-id="ffb2d-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ffb2d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ffb2d-110">Attributes</span></span>

<span data-ttu-id="ffb2d-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ffb2d-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ffb2d-112">Child Elements</span></span>

|<span data-ttu-id="ffb2d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ffb2d-113">Element</span></span>|<span data-ttu-id="ffb2d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="ffb2d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ffb2d-115">Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ffb2d-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="ffb2d-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ffb2d-117">Especifica a propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="ffb2d-118">Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ffb2d-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="ffb2d-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ffb2d-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ffb2d-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ffb2d-121">Parent Elements</span></span>

|<span data-ttu-id="ffb2d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ffb2d-122">Element</span></span>|<span data-ttu-id="ffb2d-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="ffb2d-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ffb2d-124">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ffb2d-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="ffb2d-125">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ffb2d-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="ffb2d-126">Remarks</span></span>

<span data-ttu-id="ffb2d-127">Você pode especificar um nome de propriedade ou um script para essa condição, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="ffb2d-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffb2d-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffb2d-128">See Also</span></span>

[<span data-ttu-id="ffb2d-129">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffb2d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="ffb2d-130">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ffb2d-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
