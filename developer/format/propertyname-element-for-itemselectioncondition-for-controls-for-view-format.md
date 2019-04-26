---
title: Elemento PropertyName para ItemSelectionCondition controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3955bc-f3a1-4ef6-86ac-80ffc133ad1b
caps.latest.revision: 6
ms.openlocfilehash: 28ad31be4be7be20f1f43ea1b69ad5d294de86f6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075844"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="bcb62-102">Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="bcb62-102">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="bcb62-103">Especifica a propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bcb62-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="bcb62-104">Quando essa propriedade estiver presente ou quando ela é avaliada como `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="bcb62-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="bcb62-105">Esse elemento é usado durante a definição de controles que podem ser usados por um modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="bcb62-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="bcb62-106">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento controles elemento (formato) controle elemento de configuração para controles para exibição (formato) CustomControl elemento de controle para controles para elemento CustomEntries de exibição (formato) CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para controles para elemento de exibição (formato) CustomItem CustomEntry para controles para elemento de exibição (formato) ExpressionBinding CustomItem controles para exibição (formato) Elemento ItemSelectionCondition de ExpressionBinding para controles para elemento de exibição (formato) PropertyName ItemSelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="bcb62-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bcb62-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bcb62-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bcb62-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="bcb62-108">Attributes and Elements</span></span>

<span data-ttu-id="bcb62-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="bcb62-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bcb62-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="bcb62-110">Attributes</span></span>

<span data-ttu-id="bcb62-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bcb62-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bcb62-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bcb62-112">Child Elements</span></span>

<span data-ttu-id="bcb62-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bcb62-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bcb62-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bcb62-114">Parent Elements</span></span>

|<span data-ttu-id="bcb62-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="bcb62-115">Element</span></span>|<span data-ttu-id="bcb62-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="bcb62-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bcb62-117">Elemento ItemSelectionCondition de ExpressionBinding controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="bcb62-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="bcb62-118">Define a condição que deve existir para esse controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="bcb62-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bcb62-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="bcb62-119">Text Value</span></span>

<span data-ttu-id="bcb62-120">Especifique o nome da propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bcb62-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="bcb62-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="bcb62-121">Remarks</span></span>

<span data-ttu-id="bcb62-122">Se esse elemento é usado, não é possível especificar o [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) elemento ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="bcb62-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcb62-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bcb62-123">See Also</span></span>

[<span data-ttu-id="bcb62-124">Elemento ScriptBlock para ItemSelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="bcb62-124">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="bcb62-125">Elemento ItemSelectionCondition de ExpressionBinding controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="bcb62-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="bcb62-126">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcb62-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
