---
title: Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a9b74f1882efc578f7d9ab27b8cd2f8a52833ab8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773429"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="6ffed-102">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ffed-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="6ffed-103">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="6ffed-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="6ffed-104">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle.</span><span class="sxs-lookup"><span data-stu-id="6ffed-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="6ffed-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="6ffed-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="6ffed-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento de GroupBy (Format) CustomEntry para CustomControl para o elemento de CustomItem GroupBy (Format) para CustomEntry para o elemento ExpressionBinding de GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6ffed-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6ffed-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6ffed-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ffed-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6ffed-108">Attributes and Elements</span></span>

<span data-ttu-id="6ffed-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="6ffed-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ffed-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ffed-110">Attributes</span></span>

<span data-ttu-id="6ffed-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6ffed-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ffed-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6ffed-112">Child Elements</span></span>

|<span data-ttu-id="6ffed-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ffed-113">Element</span></span>|<span data-ttu-id="6ffed-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ffed-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ffed-115">Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ffed-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="6ffed-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6ffed-116">Optional element.</span></span><br /><br /> <span data-ttu-id="6ffed-117">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6ffed-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6ffed-118">Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ffed-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="6ffed-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6ffed-119">Optional element.</span></span><br /><br /> <span data-ttu-id="6ffed-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6ffed-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6ffed-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6ffed-121">Parent Elements</span></span>

|<span data-ttu-id="6ffed-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ffed-122">Element</span></span>|<span data-ttu-id="6ffed-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ffed-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ffed-124">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ffed-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="6ffed-125">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="6ffed-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6ffed-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="6ffed-126">Remarks</span></span>

<span data-ttu-id="6ffed-127">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6ffed-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ffed-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ffed-128">See Also</span></span>

[<span data-ttu-id="6ffed-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ffed-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="6ffed-130">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ffed-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
