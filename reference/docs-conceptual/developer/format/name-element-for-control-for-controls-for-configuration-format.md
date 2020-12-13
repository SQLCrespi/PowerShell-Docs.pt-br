---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Name para Control para Controls para Configuration (formato)
description: Elemento Name para Control para Controls para Configuration (formato)
ms.openlocfilehash: 0c1c83f827482886ca742f2c0174e8383f87fb52
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666494"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="2cf2f-103">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-103">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2cf2f-104">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-104">Specifies the name of the control.</span></span> <span data-ttu-id="2cf2f-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2cf2f-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de nome de configuração (formato) para controle para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2cf2f-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2cf2f-107">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2cf2f-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2cf2f-108">Attributes and Elements</span></span>

<span data-ttu-id="2cf2f-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-109">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2cf2f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2cf2f-110">Attributes</span></span>

<span data-ttu-id="2cf2f-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2cf2f-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2cf2f-112">Child Elements</span></span>

<span data-ttu-id="2cf2f-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2cf2f-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2cf2f-114">Parent Elements</span></span>

|<span data-ttu-id="2cf2f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2cf2f-115">Element</span></span>|<span data-ttu-id="2cf2f-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="2cf2f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2cf2f-117">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-117">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="2cf2f-118">Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-118">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2cf2f-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2cf2f-119">Text Value</span></span>

<span data-ttu-id="2cf2f-120">Especifique o nome que é usado para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-120">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="2cf2f-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="2cf2f-121">Remarks</span></span>

<span data-ttu-id="2cf2f-122">O nome especificado aqui pode ser usado nos seguintes elementos para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="2cf2f-122">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="2cf2f-123">Ao criar uma tabela, lista, exibição de controle largo ou personalizada, o controle pode ser especificado pelo seguinte elemento: [elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-123">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="2cf2f-124">Ao criar outro controle comum, esse controle pode ser especificado pelo seguinte elemento: [ExpressionBinding elemento para CustomItem para controles para configuração (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-124">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="2cf2f-125">Ao criar um controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo seguinte elemento: [elemento ExpressionBinding para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-125">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="2cf2f-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2cf2f-126">See Also</span></span>

[<span data-ttu-id="2cf2f-127">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-127">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="2cf2f-128">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="2cf2f-129">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="2cf2f-130">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2cf2f-130">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="2cf2f-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cf2f-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
