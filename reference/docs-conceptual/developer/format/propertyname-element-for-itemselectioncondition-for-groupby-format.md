---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)
description: Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)
ms.openlocfilehash: 9667a389ded33d0744f0f7f8d739635a8b21d98b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666103"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="56097-103">Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="56097-103">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="56097-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="56097-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="56097-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="56097-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="56097-106">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="56097-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="56097-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para o elemento de CustomEntry GroupBy (Format) para CustomControl para GroupBy (Format) o elemento CustomItem para CustomEntry para o elemento ExpressionBinding de GroupBy (Format) para CustomItem para o elemento GroupBy (Format) ItemSelectionCondition para ExpressionBinding para o elemento GroupBy (Format) PropertyName para ItemSelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="56097-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="56097-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="56097-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="56097-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="56097-109">Attributes and Elements</span></span>

<span data-ttu-id="56097-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="56097-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="56097-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="56097-111">Attributes</span></span>

<span data-ttu-id="56097-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="56097-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="56097-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="56097-113">Child Elements</span></span>

<span data-ttu-id="56097-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="56097-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="56097-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="56097-115">Parent Elements</span></span>

|<span data-ttu-id="56097-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="56097-116">Element</span></span>|<span data-ttu-id="56097-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="56097-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56097-118">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="56097-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="56097-119">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="56097-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="56097-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="56097-120">Text Value</span></span>

<span data-ttu-id="56097-121">Especifique o nome da Propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="56097-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="56097-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="56097-122">Remarks</span></span>

<span data-ttu-id="56097-123">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="56097-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="56097-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56097-124">See Also</span></span>

[<span data-ttu-id="56097-125">Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="56097-125">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="56097-126">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="56097-126">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="56097-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="56097-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
