---
title: Elemento de controle para controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066763"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="167fa-102">Elemento Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="167fa-103">Define um controle que pode ser usado pelo modo de exibição e o nome que é usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="167fa-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="167fa-104">Elemento de exibição de ViewDefinitions elemento (formato) de (formato) do elemento de configuração (formato) controla o elemento de controle de elemento (formato) para controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="167fa-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="167fa-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="167fa-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="167fa-106">Attributes and Elements</span></span>

<span data-ttu-id="167fa-107">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `Control` elemento.</span><span class="sxs-lookup"><span data-stu-id="167fa-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="167fa-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="167fa-108">Attributes</span></span>

<span data-ttu-id="167fa-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="167fa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="167fa-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="167fa-110">Child Elements</span></span>

|<span data-ttu-id="167fa-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="167fa-111">Element</span></span>|<span data-ttu-id="167fa-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="167fa-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="167fa-113">Elemento Name para o controle para o modo de exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="167fa-114">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="167fa-114">Required element.</span></span><br /><br /> <span data-ttu-id="167fa-115">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="167fa-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="167fa-116">Elemento CustomControl para o controle para controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="167fa-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="167fa-117">Required element.</span></span><br /><br /> <span data-ttu-id="167fa-118">Define o controle usado por esta exibição.</span><span class="sxs-lookup"><span data-stu-id="167fa-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="167fa-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="167fa-119">Parent Elements</span></span>

|<span data-ttu-id="167fa-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="167fa-120">Element</span></span>|<span data-ttu-id="167fa-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="167fa-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="167fa-122">Elemento de controles (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="167fa-123">Define os controles de exibição podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="167fa-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="167fa-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="167fa-124">Remarks</span></span>

<span data-ttu-id="167fa-125">Esse controle pode ser especificado pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="167fa-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="167fa-126">Elemento CustomControlName para ExpressionBinding controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="167fa-127">Elemento CustomControlName para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="167fa-128">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="167fa-129">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="167fa-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="167fa-130">See Also</span></span>

[<span data-ttu-id="167fa-131">Elemento CustomControl para o controle para controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="167fa-132">Elemento CustomControlName para ExpressionBinding controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="167fa-133">Elemento CustomControlName para ExpressionBinding para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="167fa-134">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="167fa-135">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="167fa-136">Elemento de controles (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="167fa-137">Elemento Name para o controle para controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="167fa-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="167fa-138">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="167fa-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
