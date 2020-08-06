---
title: Elemento Control para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783799"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="81ba2-102">Elemento Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="81ba2-103">Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="81ba2-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="81ba2-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="81ba2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="81ba2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="81ba2-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="81ba2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="81ba2-106">Attributes and Elements</span></span>

<span data-ttu-id="81ba2-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Control` elemento.</span><span class="sxs-lookup"><span data-stu-id="81ba2-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="81ba2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="81ba2-108">Attributes</span></span>

<span data-ttu-id="81ba2-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="81ba2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="81ba2-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="81ba2-110">Child Elements</span></span>

|<span data-ttu-id="81ba2-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="81ba2-111">Element</span></span>|<span data-ttu-id="81ba2-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="81ba2-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="81ba2-113">Elemento Name para Control para View (Format)</span><span class="sxs-lookup"><span data-stu-id="81ba2-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="81ba2-114">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="81ba2-114">Required element.</span></span><br /><br /> <span data-ttu-id="81ba2-115">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="81ba2-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="81ba2-116">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="81ba2-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="81ba2-117">Required element.</span></span><br /><br /> <span data-ttu-id="81ba2-118">Define o controle usado por essa exibição.</span><span class="sxs-lookup"><span data-stu-id="81ba2-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="81ba2-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="81ba2-119">Parent Elements</span></span>

|<span data-ttu-id="81ba2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="81ba2-120">Element</span></span>|<span data-ttu-id="81ba2-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="81ba2-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="81ba2-122">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="81ba2-123">Define os controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="81ba2-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="81ba2-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="81ba2-124">Remarks</span></span>

<span data-ttu-id="81ba2-125">Esse controle pode ser especificado pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="81ba2-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="81ba2-126">Elemento CustomControlName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="81ba2-127">Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="81ba2-128">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="81ba2-129">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="81ba2-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81ba2-130">See Also</span></span>

[<span data-ttu-id="81ba2-131">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="81ba2-132">Elemento CustomControlName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="81ba2-133">Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="81ba2-134">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="81ba2-135">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="81ba2-136">Elemento Controls (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="81ba2-137">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="81ba2-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="81ba2-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="81ba2-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
