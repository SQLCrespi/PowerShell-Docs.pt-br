---
title: Elemento PropertyName para ItemSelectionCondition para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3955bc-f3a1-4ef6-86ac-80ffc133ad1b
caps.latest.revision: 6
ms.openlocfilehash: 28ad31be4be7be20f1f43ea1b69ad5d294de86f6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362475"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="82d2f-102">Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="82d2f-102">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="82d2f-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="82d2f-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="82d2f-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="82d2f-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="82d2f-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="82d2f-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="82d2f-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para View (Format) Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format) elemento PropertyName para ItemSelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d2f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82d2f-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82d2f-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82d2f-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="82d2f-108">Attributes and Elements</span></span>

<span data-ttu-id="82d2f-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="82d2f-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82d2f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="82d2f-110">Attributes</span></span>

<span data-ttu-id="82d2f-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="82d2f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82d2f-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="82d2f-112">Child Elements</span></span>

<span data-ttu-id="82d2f-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="82d2f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="82d2f-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="82d2f-114">Parent Elements</span></span>

|<span data-ttu-id="82d2f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="82d2f-115">Element</span></span>|<span data-ttu-id="82d2f-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="82d2f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82d2f-117">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d2f-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="82d2f-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="82d2f-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="82d2f-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="82d2f-119">Text Value</span></span>

<span data-ttu-id="82d2f-120">Especifique o nome da Propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="82d2f-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="82d2f-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="82d2f-121">Remarks</span></span>

<span data-ttu-id="82d2f-122">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="82d2f-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="82d2f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82d2f-123">See Also</span></span>

[<span data-ttu-id="82d2f-124">Elemento ScriptBlock para ItemSelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d2f-124">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="82d2f-125">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="82d2f-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="82d2f-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="82d2f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
