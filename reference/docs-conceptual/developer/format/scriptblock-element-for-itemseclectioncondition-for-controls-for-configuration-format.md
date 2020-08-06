---
title: Elemento ScriptBlock para ItemSeclectionCondition para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f44b1a7f059fa5f41c19eed93762b61eda5110e8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772885"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="d7fd6-102">Elemento ScriptBlock para ItemSeletionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="d7fd6-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d7fd6-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="d7fd6-104">Quando esse script é avaliado como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="d7fd6-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="d7fd6-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para a configuração (Format) elemento CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para o elemento Configuration (Format) ItemSelectionCondition para ExpressionBinding para controles para o elemento ScriptBlock Configuration (Format) para ItemSelectionCondition para controles para Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d7fd6-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d7fd6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d7fd6-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d7fd6-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d7fd6-108">Attributes and Elements</span></span>

<span data-ttu-id="d7fd6-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d7fd6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d7fd6-110">Attributes</span></span>

<span data-ttu-id="d7fd6-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d7fd6-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d7fd6-112">Child Elements</span></span>

<span data-ttu-id="d7fd6-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d7fd6-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d7fd6-114">Parent Elements</span></span>

|<span data-ttu-id="d7fd6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7fd6-115">Element</span></span>|<span data-ttu-id="d7fd6-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7fd6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d7fd6-117">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="d7fd6-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="d7fd6-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d7fd6-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="d7fd6-119">Text Value</span></span>

<span data-ttu-id="d7fd6-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7fd6-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="d7fd6-121">Remarks</span></span>

<span data-ttu-id="d7fd6-122">Se esse elemento for usado, você não poderá especificar o elemento [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7fd6-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7fd6-123">See Also</span></span>

[<span data-ttu-id="d7fd6-124">Elemento PropertyName para ItemSelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="d7fd6-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d7fd6-125">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="d7fd6-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="d7fd6-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7fd6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
