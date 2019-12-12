---
title: Elemento ItemSelectionCondition para ExpressionBinding para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362915"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="73c56-102">Elemento ItemSelectionCondition para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="73c56-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="73c56-103">Define a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="73c56-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="73c56-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="73c56-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="73c56-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para configuração (Format) Elemento ItemSelectionCondition para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="73c56-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="73c56-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="73c56-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="73c56-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="73c56-107">Attributes and Elements</span></span>

<span data-ttu-id="73c56-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `ItemSelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="73c56-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="73c56-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="73c56-109">Attributes</span></span>

<span data-ttu-id="73c56-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="73c56-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="73c56-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="73c56-111">Child Elements</span></span>

|<span data-ttu-id="73c56-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="73c56-112">Element</span></span>|<span data-ttu-id="73c56-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="73c56-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="73c56-114">Elemento PropertyName para ItemSelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="73c56-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="73c56-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="73c56-115">Optional element.</span></span><br /><br /> <span data-ttu-id="73c56-116">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="73c56-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="73c56-117">Elemento ScriptBlock para ItemSelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="73c56-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="73c56-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="73c56-118">Optional element.</span></span><br /><br /> <span data-ttu-id="73c56-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="73c56-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="73c56-120">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="73c56-120">Parent Elements</span></span>

|<span data-ttu-id="73c56-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="73c56-121">Element</span></span>|<span data-ttu-id="73c56-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="73c56-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="73c56-123">Elemento ExpressionBinding para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="73c56-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="73c56-124">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="73c56-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="73c56-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="73c56-125">Remarks</span></span>

<span data-ttu-id="73c56-126">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="73c56-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="73c56-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73c56-127">See Also</span></span>

[<span data-ttu-id="73c56-128">Elemento PropertyName para ItemSelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="73c56-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="73c56-129">Elemento ScriptBlock para ItemSelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="73c56-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="73c56-130">Elemento ExpressionBinding para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="73c56-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="73c56-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="73c56-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
