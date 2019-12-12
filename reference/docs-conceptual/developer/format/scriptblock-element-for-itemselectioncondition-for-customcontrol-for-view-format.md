---
title: Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 946cd2b5-ac37-4a13-bb49-29fbc70ec8d7
caps.latest.revision: 6
ms.openlocfilehash: 0c07ab0e5d04c4056a7e7215bfa55773bfccb41d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362065"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="0333d-102">Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0333d-102">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="0333d-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0333d-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="0333d-104">Quando esse script é avaliado como `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="0333d-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="0333d-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="0333d-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="0333d-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento ExpressionBinding View (Format) para CustomItem para CustomControl para o elemento View (Format) ItemSelectionCondition para a associação de expressão para CustomControl para o elemento ScriptBlock (Format) View para ItemSelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0333d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0333d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0333d-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0333d-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0333d-108">Attributes and Elements</span></span>

<span data-ttu-id="0333d-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="0333d-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0333d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0333d-110">Attributes</span></span>

<span data-ttu-id="0333d-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0333d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0333d-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="0333d-112">Child Elements</span></span>

<span data-ttu-id="0333d-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0333d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0333d-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="0333d-114">Parent Elements</span></span>

|<span data-ttu-id="0333d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0333d-115">Element</span></span>|<span data-ttu-id="0333d-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="0333d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0333d-117">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0333d-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="0333d-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="0333d-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0333d-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="0333d-119">Text Value</span></span>

<span data-ttu-id="0333d-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="0333d-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="0333d-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="0333d-121">Remarks</span></span>

<span data-ttu-id="0333d-122">Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="0333d-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="0333d-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0333d-123">See Also</span></span>

[<span data-ttu-id="0333d-124">Elemento PropertyName para ItemSelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0333d-124">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="0333d-125">Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0333d-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="0333d-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0333d-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
