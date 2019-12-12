---
title: Elemento ScriptBlock para ItemSelectionCondition para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4191157-bf01-4831-b221-6f8cc581cd53
caps.latest.revision: 6
ms.openlocfilehash: 0cbefbb48427b56d4ae2a5ae27c7726dcfad7b84
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364915"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="c9569-102">Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c9569-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="c9569-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="c9569-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="c9569-104">Quando esse script é avaliado como `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="c9569-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="c9569-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="c9569-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="c9569-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para View (Format) Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format) elemento ScriptBlock para ItemSelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="c9569-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c9569-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c9569-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c9569-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="c9569-108">Attributes and Elements</span></span>

<span data-ttu-id="c9569-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="c9569-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c9569-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c9569-110">Attributes</span></span>

<span data-ttu-id="c9569-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c9569-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c9569-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="c9569-112">Child Elements</span></span>

<span data-ttu-id="c9569-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c9569-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c9569-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="c9569-114">Parent Elements</span></span>

|<span data-ttu-id="c9569-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9569-115">Element</span></span>|<span data-ttu-id="c9569-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9569-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c9569-117">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="c9569-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="c9569-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="c9569-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c9569-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="c9569-119">Text Value</span></span>

<span data-ttu-id="c9569-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="c9569-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9569-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="c9569-121">Remarks</span></span>

<span data-ttu-id="c9569-122">Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="c9569-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9569-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9569-123">See Also</span></span>

[<span data-ttu-id="c9569-124">Elemento PropertyName para ItemSelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="c9569-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="c9569-125">Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="c9569-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="c9569-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9569-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
