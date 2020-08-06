---
title: Elemento PropertyName para ItemSeclectionCondition para controles para configuração (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0e304af1dbe816753d6dcd1dd8149f950f2a0941
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785584"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="1d2b1-102">Elemento PropertyName para ItemSelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="1d2b1-102">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="1d2b1-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="1d2b1-104">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="1d2b1-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="1d2b1-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para a configuração (Format) elemento CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para o elemento Configuration (Format) ItemSelectionCondition para ExpressionBinding para controles para o elemento de configuração (Format) PropertyName para ItemSeclectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="1d2b1-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1d2b1-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1d2b1-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1d2b1-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1d2b1-108">Attributes and Elements</span></span>

<span data-ttu-id="1d2b1-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1d2b1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1d2b1-110">Attributes</span></span>

<span data-ttu-id="1d2b1-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1d2b1-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1d2b1-112">Child Elements</span></span>

<span data-ttu-id="1d2b1-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1d2b1-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1d2b1-114">Parent Elements</span></span>

|<span data-ttu-id="1d2b1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d2b1-115">Element</span></span>|<span data-ttu-id="1d2b1-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d2b1-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d2b1-117">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="1d2b1-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="1d2b1-118">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1d2b1-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1d2b1-119">Text Value</span></span>

<span data-ttu-id="1d2b1-120">Especifique o nome da Propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d2b1-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="1d2b1-121">Remarks</span></span>

<span data-ttu-id="1d2b1-122">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="1d2b1-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d2b1-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d2b1-123">See Also</span></span>

[<span data-ttu-id="1d2b1-124">Elemento ScriptBlock para ItemSeletionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="1d2b1-124">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="1d2b1-125">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="1d2b1-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="1d2b1-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d2b1-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
