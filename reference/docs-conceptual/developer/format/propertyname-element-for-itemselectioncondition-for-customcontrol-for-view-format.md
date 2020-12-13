---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ItemSelectionCondition para CustomControl para View (formato)
description: Elemento PropertyName para ItemSelectionCondition para CustomControl para View (formato)
ms.openlocfilehash: 5687bb781ce2db27b875f829147ee8b436f04adc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666120"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="3922d-103">Elemento PropertyName para ItemSelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="3922d-103">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="3922d-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3922d-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="3922d-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="3922d-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="3922d-106">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="3922d-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="3922d-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para exibição (Format) o elemento ExpressionBinding para CustomItem para CustomControl para o elemento View (Format) ItemSelectionCondition para a associação de expressão para CustomControl para o elemento View (Format) PropertyName para ItemSelectionCondition para CustomControl para View (Format</span><span class="sxs-lookup"><span data-stu-id="3922d-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="3922d-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3922d-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3922d-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3922d-109">Attributes and Elements</span></span>

<span data-ttu-id="3922d-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="3922d-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3922d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3922d-111">Attributes</span></span>

<span data-ttu-id="3922d-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="3922d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3922d-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="3922d-113">Child Elements</span></span>

<span data-ttu-id="3922d-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="3922d-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3922d-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="3922d-115">Parent Elements</span></span>

|<span data-ttu-id="3922d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="3922d-116">Element</span></span>|<span data-ttu-id="3922d-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="3922d-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3922d-118">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="3922d-118">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="3922d-119">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="3922d-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3922d-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="3922d-120">Text Value</span></span>

<span data-ttu-id="3922d-121">Especifique o nome da Propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3922d-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="3922d-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="3922d-122">Remarks</span></span>

<span data-ttu-id="3922d-123">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="3922d-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="3922d-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3922d-124">See Also</span></span>

[<span data-ttu-id="3922d-125">Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="3922d-125">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3922d-126">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="3922d-126">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="3922d-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3922d-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
