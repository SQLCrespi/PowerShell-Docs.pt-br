---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ItemSelectionCondition para Controls para Configuration (formato)
description: Elemento PropertyName para ItemSelectionCondition para Controls para Configuration (formato)
ms.openlocfilehash: 860683eb54b2a3579767640c1d3f0937897b8f8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655136"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="aa430-103">Elemento PropertyName para ItemSelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aa430-103">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="aa430-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="aa430-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="aa430-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="aa430-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="aa430-106">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="aa430-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="aa430-107">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para a configuração (Format) elemento CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para o elemento Configuration (Format) ItemSelectionCondition para ExpressionBinding para controles para o elemento de configuração (Format) PropertyName para ItemSeclectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="aa430-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aa430-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa430-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa430-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="aa430-109">Attributes and Elements</span></span>

<span data-ttu-id="aa430-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="aa430-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa430-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa430-111">Attributes</span></span>

<span data-ttu-id="aa430-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="aa430-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa430-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="aa430-113">Child Elements</span></span>

<span data-ttu-id="aa430-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="aa430-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aa430-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="aa430-115">Parent Elements</span></span>

|<span data-ttu-id="aa430-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa430-116">Element</span></span>|<span data-ttu-id="aa430-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="aa430-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa430-118">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aa430-118">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="aa430-119">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="aa430-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="aa430-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="aa430-120">Text Value</span></span>

<span data-ttu-id="aa430-121">Especifique o nome da Propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="aa430-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa430-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="aa430-122">Remarks</span></span>

<span data-ttu-id="aa430-123">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="aa430-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa430-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa430-124">See Also</span></span>

[<span data-ttu-id="aa430-125">Elemento ScriptBlock para ItemSeletionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aa430-125">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="aa430-126">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="aa430-126">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="aa430-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa430-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
