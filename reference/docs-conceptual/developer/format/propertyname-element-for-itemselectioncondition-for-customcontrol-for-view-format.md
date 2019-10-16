---
title: Elemento PropertyName para ItemSelectionCondition para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b12006-8d52-486b-91a3-e6224ca80e56
caps.latest.revision: 6
ms.openlocfilehash: 52d0b0816eaef6752220e0c3b1249e5a0e44a3ee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362435"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="8c479-102">Elemento PropertyName para ItemSelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="8c479-102">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="8c479-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="8c479-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="8c479-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="8c479-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="8c479-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="8c479-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="8c479-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento ExpressionBinding View (Format) para CustomItem para CustomControl para o elemento View (Format) ItemSelectionCondition para a associação de expressão para CustomControl para o elemento View (Format) PropertyName para ItemSelectionCondition para CustomControl para exibição (formato</span><span class="sxs-lookup"><span data-stu-id="8c479-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="8c479-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8c479-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c479-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8c479-108">Attributes and Elements</span></span>

<span data-ttu-id="8c479-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="8c479-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c479-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8c479-110">Attributes</span></span>

<span data-ttu-id="8c479-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8c479-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c479-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="8c479-112">Child Elements</span></span>

<span data-ttu-id="8c479-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8c479-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8c479-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="8c479-114">Parent Elements</span></span>

|<span data-ttu-id="8c479-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c479-115">Element</span></span>|<span data-ttu-id="8c479-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c479-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c479-117">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8c479-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="8c479-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="8c479-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8c479-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="8c479-119">Text Value</span></span>

<span data-ttu-id="8c479-120">Especifique o nome da Propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="8c479-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c479-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="8c479-121">Remarks</span></span>

<span data-ttu-id="8c479-122">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="8c479-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c479-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8c479-123">See Also</span></span>

[<span data-ttu-id="8c479-124">Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c479-124">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8c479-125">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8c479-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="8c479-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c479-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
