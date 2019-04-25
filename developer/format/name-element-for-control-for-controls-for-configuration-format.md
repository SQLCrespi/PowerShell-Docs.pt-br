---
title: Nome de elemento para o controle para controles para configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065182"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="5a0a8-102">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="5a0a8-103">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-103">Specifies the name of the control.</span></span> <span data-ttu-id="5a0a8-104">Esse elemento é usado durante a definição de um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="5a0a8-105">Elemento de controles de (formato) do elemento de configuração do elemento de controle de configuração (formato) para controles para o elemento de nome de configuração (formato) para o controle para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5a0a8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5a0a8-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="5a0a8-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="5a0a8-107">Attributes and Elements</span></span>

<span data-ttu-id="5a0a8-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5a0a8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a0a8-109">Attributes</span></span>

<span data-ttu-id="5a0a8-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5a0a8-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5a0a8-111">Child Elements</span></span>

<span data-ttu-id="5a0a8-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5a0a8-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5a0a8-113">Parent Elements</span></span>

|<span data-ttu-id="5a0a8-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a0a8-114">Element</span></span>|<span data-ttu-id="5a0a8-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5a0a8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a0a8-116">Elemento de controle para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="5a0a8-117">Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e o nome que é usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5a0a8-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="5a0a8-118">Text Value</span></span>

<span data-ttu-id="5a0a8-119">Especifique o nome que é usado para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a0a8-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="5a0a8-120">Remarks</span></span>

<span data-ttu-id="5a0a8-121">O nome especificado aqui pode ser usado nos elementos a seguir para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="5a0a8-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="5a0a8-122">Ao criar uma tabela, a lista, o modo de exibição de controle personalizado ou ampla, o controle pode ser especificado pelo elemento a seguir: [Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="5a0a8-123">Ao criar outro controle comum, esse controle pode ser especificado pelo elemento a seguir: [Elemento ExpressionBinding para CustomItem para controles de configuração (formato)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="5a0a8-124">Ao criar um controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo elemento a seguir: [Elemento ExpressionBinding para CustomItem controles para exibição (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="5a0a8-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a0a8-125">See Also</span></span>

[<span data-ttu-id="5a0a8-126">Elemento de controle para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="5a0a8-127">Elemento ExpressionBinding para CustomItem para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="5a0a8-128">Elemento ExpressionBinding para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5a0a8-129">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5a0a8-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="5a0a8-130">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a0a8-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
