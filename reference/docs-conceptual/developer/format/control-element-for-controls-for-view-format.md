---
title: Elemento Control para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363465"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="19dfc-102">Elemento Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="19dfc-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="19dfc-103">Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="19dfc-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="19dfc-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="19dfc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="19dfc-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="19dfc-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="19dfc-106">Attributes and Elements</span></span>

<span data-ttu-id="19dfc-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Control`.</span><span class="sxs-lookup"><span data-stu-id="19dfc-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="19dfc-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="19dfc-108">Attributes</span></span>

<span data-ttu-id="19dfc-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="19dfc-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="19dfc-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="19dfc-110">Child Elements</span></span>

|<span data-ttu-id="19dfc-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="19dfc-111">Element</span></span>|<span data-ttu-id="19dfc-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="19dfc-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="19dfc-113">Elemento Name para Control para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="19dfc-114">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="19dfc-114">Required element.</span></span><br /><br /> <span data-ttu-id="19dfc-115">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="19dfc-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="19dfc-116">Elemento CustomControl para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="19dfc-117">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="19dfc-117">Required element.</span></span><br /><br /> <span data-ttu-id="19dfc-118">Define o controle usado por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="19dfc-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="19dfc-119">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="19dfc-119">Parent Elements</span></span>

|<span data-ttu-id="19dfc-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="19dfc-120">Element</span></span>|<span data-ttu-id="19dfc-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="19dfc-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="19dfc-122">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="19dfc-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="19dfc-123">Define os controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="19dfc-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="19dfc-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="19dfc-124">Remarks</span></span>

<span data-ttu-id="19dfc-125">Esse controle pode ser especificado pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="19dfc-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="19dfc-126">Elemento CustomControlName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="19dfc-127">Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="19dfc-128">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="19dfc-129">Elemento CustomControlName para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="19dfc-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19dfc-130">See Also</span></span>

[<span data-ttu-id="19dfc-131">Elemento CustomControl para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="19dfc-132">Elemento CustomControlName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="19dfc-133">Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="19dfc-134">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="19dfc-135">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="19dfc-136">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="19dfc-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="19dfc-137">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="19dfc-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="19dfc-138">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="19dfc-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
