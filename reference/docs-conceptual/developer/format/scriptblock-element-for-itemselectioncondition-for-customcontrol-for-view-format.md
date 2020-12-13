---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)
description: Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)
ms.openlocfilehash: d762f400f5bb52af314093079fe94223c56d3f31
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665128"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="c543f-103">Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c543f-103">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="c543f-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="c543f-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="c543f-105">Quando esse script é avaliado como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="c543f-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="c543f-106">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="c543f-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="c543f-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento ExpressionBinding View (Format) para CustomItem para CustomControl para o elemento View (Format) ItemSelectionCondition para a associação de expressão para CustomControl para o elemento ScriptBlock View (Format) para ItemSelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="c543f-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c543f-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c543f-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c543f-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="c543f-109">Attributes and Elements</span></span>

<span data-ttu-id="c543f-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="c543f-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c543f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c543f-111">Attributes</span></span>

<span data-ttu-id="c543f-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="c543f-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c543f-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="c543f-113">Child Elements</span></span>

<span data-ttu-id="c543f-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="c543f-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c543f-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="c543f-115">Parent Elements</span></span>

|<span data-ttu-id="c543f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c543f-116">Element</span></span>|<span data-ttu-id="c543f-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="c543f-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c543f-118">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="c543f-118">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="c543f-119">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="c543f-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c543f-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="c543f-120">Text Value</span></span>

<span data-ttu-id="c543f-121">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="c543f-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="c543f-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="c543f-122">Remarks</span></span>

<span data-ttu-id="c543f-123">Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="c543f-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="c543f-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c543f-124">See Also</span></span>

[<span data-ttu-id="c543f-125">Elemento PropertyName para ItemSelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c543f-125">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c543f-126">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="c543f-126">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="c543f-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c543f-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
