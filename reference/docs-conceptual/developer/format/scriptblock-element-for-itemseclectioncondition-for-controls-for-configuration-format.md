---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ItemSeletionCondition para Controls para Configuration (formato)
description: Elemento ScriptBlock para ItemSeletionCondition para Controls para Configuration (formato)
ms.openlocfilehash: 853130da4489e571d7f4026a8d65d029d1889f9b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665225"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="0f092-103">Elemento ScriptBlock para ItemSeletionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0f092-103">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="0f092-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0f092-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="0f092-105">Quando esse script é avaliado como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="0f092-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="0f092-106">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="0f092-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="0f092-107">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para a configuração (Format) elemento CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para o elemento Configuration (Format) ItemSelectionCondition para ExpressionBinding para controles para o elemento ScriptBlock Configuration (Format) para ItemSelectionCondition para controles para Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="0f092-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0f092-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0f092-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f092-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0f092-109">Attributes and Elements</span></span>

<span data-ttu-id="0f092-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="0f092-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f092-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="0f092-111">Attributes</span></span>

<span data-ttu-id="0f092-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0f092-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f092-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0f092-113">Child Elements</span></span>

<span data-ttu-id="0f092-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0f092-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f092-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0f092-115">Parent Elements</span></span>

|<span data-ttu-id="0f092-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f092-116">Element</span></span>|<span data-ttu-id="0f092-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="0f092-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f092-118">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0f092-118">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="0f092-119">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="0f092-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0f092-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0f092-120">Text Value</span></span>

<span data-ttu-id="0f092-121">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="0f092-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f092-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="0f092-122">Remarks</span></span>

<span data-ttu-id="0f092-123">Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="0f092-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f092-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f092-124">See Also</span></span>

[<span data-ttu-id="0f092-125">Elemento PropertyName para ItemSelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0f092-125">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="0f092-126">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0f092-126">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="0f092-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f092-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
