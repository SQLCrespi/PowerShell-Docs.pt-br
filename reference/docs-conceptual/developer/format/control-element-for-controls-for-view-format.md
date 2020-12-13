---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Control para Controls para View (formato)
description: Elemento Control para Controls para View (formato)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668075"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="ec335-103">Elemento Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-103">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="ec335-104">Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="ec335-104">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="ec335-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="ec335-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ec335-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ec335-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec335-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ec335-107">Attributes and Elements</span></span>

<span data-ttu-id="ec335-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Control` elemento.</span><span class="sxs-lookup"><span data-stu-id="ec335-108">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec335-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec335-109">Attributes</span></span>

<span data-ttu-id="ec335-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ec335-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ec335-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ec335-111">Child Elements</span></span>

|<span data-ttu-id="ec335-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec335-112">Element</span></span>|<span data-ttu-id="ec335-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec335-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec335-114">Elemento Name para Control para View (Format)</span><span class="sxs-lookup"><span data-stu-id="ec335-114">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="ec335-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="ec335-115">Required element.</span></span><br /><br /> <span data-ttu-id="ec335-116">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="ec335-116">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="ec335-117">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-117">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="ec335-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="ec335-118">Required element.</span></span><br /><br /> <span data-ttu-id="ec335-119">Define o controle usado por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="ec335-119">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ec335-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ec335-120">Parent Elements</span></span>

|<span data-ttu-id="ec335-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec335-121">Element</span></span>|<span data-ttu-id="ec335-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec335-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec335-123">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-123">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="ec335-124">Define os controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="ec335-124">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ec335-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="ec335-125">Remarks</span></span>

<span data-ttu-id="ec335-126">Esse controle pode ser especificado pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="ec335-126">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="ec335-127">Elemento CustomControlName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-127">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="ec335-128">Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-128">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="ec335-129">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-129">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="ec335-130">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-130">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="ec335-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec335-131">See Also</span></span>

[<span data-ttu-id="ec335-132">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-132">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ec335-133">Elemento CustomControlName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-133">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ec335-134">Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-134">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ec335-135">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ec335-136">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-136">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ec335-137">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-137">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="ec335-138">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="ec335-138">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ec335-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec335-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
