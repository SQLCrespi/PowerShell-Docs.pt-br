---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)
description: Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648042"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="ee282-103">Elemento ItemSelectionCondition para ExpressionBinding para CustomControl (formato)</span><span class="sxs-lookup"><span data-stu-id="ee282-103">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="ee282-104">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="ee282-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="ee282-105">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle.</span><span class="sxs-lookup"><span data-stu-id="ee282-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="ee282-106">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="ee282-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ee282-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) CustomItem para CustomEntry para o elemento View (Format) ExpressionBinding para CustomItem para CustomControl para o elemento View (Format) ItemSelectionCondition para a associação de expressão para CustomControl para a exibição (Format)</span><span class="sxs-lookup"><span data-stu-id="ee282-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ee282-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ee282-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee282-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ee282-109">Attributes and Elements</span></span>

<span data-ttu-id="ee282-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="ee282-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ee282-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ee282-111">Attributes</span></span>

<span data-ttu-id="ee282-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ee282-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ee282-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ee282-113">Child Elements</span></span>

|<span data-ttu-id="ee282-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee282-114">Element</span></span>|<span data-ttu-id="ee282-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee282-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee282-116">Elemento PropertyName para ItemSelectionCondition para CustomControl para exibição (formato</span><span class="sxs-lookup"><span data-stu-id="ee282-116">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ee282-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ee282-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ee282-118">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="ee282-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="ee282-119">Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ee282-119">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ee282-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ee282-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ee282-121">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="ee282-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ee282-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ee282-122">Parent Elements</span></span>

|<span data-ttu-id="ee282-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee282-123">Element</span></span>|<span data-ttu-id="ee282-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee282-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee282-125">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ee282-125">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="ee282-126">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="ee282-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ee282-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="ee282-127">Remarks</span></span>

<span data-ttu-id="ee282-128">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="ee282-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee282-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee282-129">See Also</span></span>

[<span data-ttu-id="ee282-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee282-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="ee282-131">Elemento ExpressionBinding para CustomItem para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ee282-131">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
