---
title: Elemento ScriptBlock para ItemSelectionCondition controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4191157-bf01-4831-b221-6f8cc581cd53
caps.latest.revision: 6
ms.openlocfilehash: 0cbefbb48427b56d4ae2a5ae27c7726dcfad7b84
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064706"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="2b3c1-102">Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2b3c1-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="2b3c1-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="2b3c1-104">Quando esse script é avaliado para `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="2b3c1-105">Esse elemento é usado durante a definição de controles que podem ser usados por um modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="2b3c1-106">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento controles elemento (formato) controle elemento de configuração para controles para exibição (formato) CustomControl elemento de controle para controles para elemento CustomEntries de exibição (formato) CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para controles para elemento de exibição (formato) CustomItem CustomEntry para controles para elemento de exibição (formato) ExpressionBinding CustomItem controles para exibição (formato) Elemento ItemSelectionCondition de ExpressionBinding para controles para elemento de exibição (formato) ScriptBlock ItemSelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="2b3c1-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b3c1-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2b3c1-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b3c1-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="2b3c1-108">Attributes and Elements</span></span>

<span data-ttu-id="2b3c1-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b3c1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2b3c1-110">Attributes</span></span>

<span data-ttu-id="2b3c1-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b3c1-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2b3c1-112">Child Elements</span></span>

<span data-ttu-id="2b3c1-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2b3c1-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2b3c1-114">Parent Elements</span></span>

|<span data-ttu-id="2b3c1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b3c1-115">Element</span></span>|<span data-ttu-id="2b3c1-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b3c1-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b3c1-117">Elemento ItemSelectionCondition de ExpressionBinding controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="2b3c1-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="2b3c1-118">Define a condição que deve existir para esse controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2b3c1-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2b3c1-119">Text Value</span></span>

<span data-ttu-id="2b3c1-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b3c1-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="2b3c1-121">Remarks</span></span>

<span data-ttu-id="2b3c1-122">Se esse elemento é usado, não é possível especificar o [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) elemento ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="2b3c1-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b3c1-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b3c1-123">See Also</span></span>

[<span data-ttu-id="2b3c1-124">Elemento PropertyName para ItemSelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="2b3c1-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="2b3c1-125">Elemento ItemSelectionCondition de ExpressionBinding controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="2b3c1-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="2b3c1-126">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b3c1-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
