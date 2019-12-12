---
title: Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365285"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="43418-102">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="43418-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="43418-103">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="43418-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="43418-104">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle.</span><span class="sxs-lookup"><span data-stu-id="43418-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="43418-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="43418-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="43418-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) CustomItem elemento para CustomEntry para o elemento ExpressionBinding de GroupBy (Format) para CustomItem para o elemento ItemSelectionCondition de GroupBy (Format) para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="43418-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="43418-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="43418-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="43418-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="43418-108">Attributes and Elements</span></span>

<span data-ttu-id="43418-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ItemSelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="43418-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="43418-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="43418-110">Attributes</span></span>

<span data-ttu-id="43418-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="43418-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="43418-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="43418-112">Child Elements</span></span>

|<span data-ttu-id="43418-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="43418-113">Element</span></span>|<span data-ttu-id="43418-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="43418-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="43418-115">Elemento PropertyName para ItemSelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="43418-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="43418-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="43418-116">Optional element.</span></span><br /><br /> <span data-ttu-id="43418-117">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="43418-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="43418-118">Elemento ScriptBlock para ItemSelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="43418-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="43418-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="43418-119">Optional element.</span></span><br /><br /> <span data-ttu-id="43418-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="43418-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="43418-121">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="43418-121">Parent Elements</span></span>

|<span data-ttu-id="43418-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="43418-122">Element</span></span>|<span data-ttu-id="43418-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="43418-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="43418-124">Elemento ExpressionBinding para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="43418-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="43418-125">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="43418-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="43418-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="43418-126">Remarks</span></span>

<span data-ttu-id="43418-127">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="43418-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="43418-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="43418-128">See Also</span></span>

[<span data-ttu-id="43418-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="43418-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="43418-130">Elemento ExpressionBinding para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="43418-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
