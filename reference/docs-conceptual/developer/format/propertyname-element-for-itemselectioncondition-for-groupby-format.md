---
title: Elemento PropertyName para ItemSelectionCondition para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 221cbdc2-f794-4f3a-9d40-bfdd8cba1013
caps.latest.revision: 6
ms.openlocfilehash: aae65789cf5572cbcc9251eca802a2d43065e49f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362405"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="1f557-102">Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1f557-102">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="1f557-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1f557-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="1f557-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="1f557-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="1f557-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="1f557-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1f557-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento GroupBy (Format) CustomItem para CustomEntry para o elemento ExpressionBinding de GroupBy (Format) para CustomItem para o elemento de ItemSelectionCondition GroupBy (Format) para ExpressionBinding para o elemento GroupBy (Format) PropertyName para ItemSelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1f557-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1f557-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1f557-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1f557-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1f557-108">Attributes and Elements</span></span>

<span data-ttu-id="1f557-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="1f557-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1f557-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1f557-110">Attributes</span></span>

<span data-ttu-id="1f557-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1f557-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1f557-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="1f557-112">Child Elements</span></span>

<span data-ttu-id="1f557-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1f557-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1f557-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="1f557-114">Parent Elements</span></span>

|<span data-ttu-id="1f557-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f557-115">Element</span></span>|<span data-ttu-id="1f557-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f557-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1f557-117">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1f557-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="1f557-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="1f557-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1f557-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="1f557-119">Text Value</span></span>

<span data-ttu-id="1f557-120">Especifique o nome da Propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1f557-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f557-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="1f557-121">Remarks</span></span>

<span data-ttu-id="1f557-122">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="1f557-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f557-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1f557-123">See Also</span></span>

[<span data-ttu-id="1f557-124">Elemento ScriptBlock para ItemSelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1f557-124">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="1f557-125">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1f557-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="1f557-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f557-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
