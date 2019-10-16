---
title: Elemento ScriptBlock para ItemSeclectionCondition para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f7aec9-7b01-4370-84f4-1e58508a851f
caps.latest.revision: 6
ms.openlocfilehash: e92b2dfff07358132c480c47c34279e5365fe400
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362115"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="58006-102">Elemento ScriptBlock para ItemSeletionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="58006-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="58006-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="58006-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="58006-104">Quando esse script é avaliado como `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="58006-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="58006-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="58006-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="58006-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para configuração (Format) Elemento ItemSelectionCondition para ExpressionBinding para controles de elemento de ScriptBlock de configuração (Format) para ItemSelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="58006-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="58006-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="58006-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58006-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="58006-108">Attributes and Elements</span></span>

<span data-ttu-id="58006-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="58006-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="58006-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="58006-110">Attributes</span></span>

<span data-ttu-id="58006-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="58006-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="58006-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="58006-112">Child Elements</span></span>

<span data-ttu-id="58006-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="58006-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58006-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="58006-114">Parent Elements</span></span>

|<span data-ttu-id="58006-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="58006-115">Element</span></span>|<span data-ttu-id="58006-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="58006-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58006-117">Elemento ItemSelectionCondition para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="58006-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="58006-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="58006-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="58006-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="58006-119">Text Value</span></span>

<span data-ttu-id="58006-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="58006-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="58006-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="58006-121">Remarks</span></span>

<span data-ttu-id="58006-122">Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="58006-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="58006-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58006-123">See Also</span></span>

[<span data-ttu-id="58006-124">Elemento PropertyName para ItemSeclectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="58006-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="58006-125">Elemento ItemSelectionCondition para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="58006-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="58006-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58006-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
