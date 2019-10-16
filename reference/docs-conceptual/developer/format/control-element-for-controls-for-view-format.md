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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363465"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="9ff53-102">Elemento Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="9ff53-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="9ff53-103">Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="9ff53-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="9ff53-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9ff53-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ff53-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9ff53-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9ff53-106">Attributes and Elements</span></span>

<span data-ttu-id="9ff53-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Control`.</span><span class="sxs-lookup"><span data-stu-id="9ff53-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ff53-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ff53-108">Attributes</span></span>

<span data-ttu-id="9ff53-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9ff53-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9ff53-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="9ff53-110">Child Elements</span></span>

|<span data-ttu-id="9ff53-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ff53-111">Element</span></span>|<span data-ttu-id="9ff53-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ff53-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ff53-113">Elemento Name para Control para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="9ff53-114">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="9ff53-114">Required element.</span></span><br /><br /> <span data-ttu-id="9ff53-115">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="9ff53-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="9ff53-116">Elemento CustomControl para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="9ff53-117">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="9ff53-117">Required element.</span></span><br /><br /> <span data-ttu-id="9ff53-118">Define o controle usado por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="9ff53-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9ff53-119">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="9ff53-119">Parent Elements</span></span>

|<span data-ttu-id="9ff53-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ff53-120">Element</span></span>|<span data-ttu-id="9ff53-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ff53-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ff53-122">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="9ff53-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="9ff53-123">Define os controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="9ff53-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9ff53-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="9ff53-124">Remarks</span></span>

<span data-ttu-id="9ff53-125">Esse controle pode ser especificado pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="9ff53-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="9ff53-126">Elemento CustomControlName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="9ff53-127">Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="9ff53-128">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="9ff53-129">Elemento CustomControlName para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="9ff53-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ff53-130">See Also</span></span>

[<span data-ttu-id="9ff53-131">Elemento CustomControl para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="9ff53-132">Elemento CustomControlName para ExpressionBinding para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="9ff53-133">Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9ff53-134">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9ff53-135">Elemento CustomControlName para ExpressionBinding para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9ff53-136">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="9ff53-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="9ff53-137">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ff53-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="9ff53-138">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ff53-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
