---
title: Elemento ItemSelectionCondition para ExpressionBinding para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e8e3ea64fd947fbb2b98c410ac08533f386c9505
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781198"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="cc898-102">Elemento ItemSelectionCondition para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc898-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="cc898-103">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="cc898-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="cc898-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="cc898-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="cc898-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento viewbinding de exibição (Format) para CustomItem para controles para o elemento View (Format) ItemSelectionCondition de ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="cc898-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc898-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc898-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc898-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="cc898-107">Attributes and Elements</span></span>

<span data-ttu-id="cc898-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="cc898-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc898-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc898-109">Attributes</span></span>

<span data-ttu-id="cc898-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="cc898-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc898-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="cc898-111">Child Elements</span></span>

|<span data-ttu-id="cc898-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc898-112">Element</span></span>|<span data-ttu-id="cc898-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc898-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc898-114">Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc898-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="cc898-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="cc898-115">Optional element.</span></span><br /><br /> <span data-ttu-id="cc898-116">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="cc898-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="cc898-117">Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc898-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="cc898-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="cc898-118">Optional element.</span></span><br /><br /> <span data-ttu-id="cc898-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="cc898-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cc898-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="cc898-120">Parent Elements</span></span>

|<span data-ttu-id="cc898-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc898-121">Element</span></span>|<span data-ttu-id="cc898-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc898-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc898-123">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc898-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="cc898-124">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="cc898-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cc898-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="cc898-125">Remarks</span></span>

<span data-ttu-id="cc898-126">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="cc898-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc898-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc898-127">See Also</span></span>

[<span data-ttu-id="cc898-128">Elemento PropertyName para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc898-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="cc898-129">Elemento ScriptBlock para ItemSelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc898-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="cc898-130">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="cc898-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="cc898-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc898-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
