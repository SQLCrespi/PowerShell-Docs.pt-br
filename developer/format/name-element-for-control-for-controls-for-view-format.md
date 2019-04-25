---
title: Nome de elemento para o controle para controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065081"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="5970b-102">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="5970b-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="5970b-103">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="5970b-103">Specifies the name of the control.</span></span>

<span data-ttu-id="5970b-104">Configuração elemento (formato) elemento ViewDefinitions (formato) exibição elemento (formato) controla elemento de controle de elemento (formato) para controles para elemento de nome de exibição (formato) para o controle para o modo de exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5970b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5970b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5970b-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5970b-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="5970b-106">Attributes and Elements</span></span>

<span data-ttu-id="5970b-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.</span><span class="sxs-lookup"><span data-stu-id="5970b-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5970b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5970b-108">Attributes</span></span>

<span data-ttu-id="5970b-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5970b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5970b-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5970b-110">Child Elements</span></span>

<span data-ttu-id="5970b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5970b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5970b-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5970b-112">Parent Elements</span></span>

|<span data-ttu-id="5970b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5970b-113">Element</span></span>|<span data-ttu-id="5970b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="5970b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5970b-115">Elemento de controle para controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5970b-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="5970b-116">Define um controle que pode ser usado pelo modo de exibição e o nome que é usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="5970b-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5970b-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="5970b-117">Text Value</span></span>

<span data-ttu-id="5970b-118">Especifique o nome que é usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="5970b-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="5970b-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="5970b-119">Remarks</span></span>

<span data-ttu-id="5970b-120">O nome especificado aqui pode ser usado nos elementos a seguir para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="5970b-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="5970b-121">Ao criar uma tabela, a lista, o modo de exibição de controle personalizado ou ampla, o controle pode ser especificado pelo elemento a seguir: [Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="5970b-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="5970b-122">Quando a criação de outro controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo elemento a seguir: [Elemento ExpressionBinding para CustomItem controles para exibição (formato)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="5970b-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="5970b-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5970b-123">See Also</span></span>

[<span data-ttu-id="5970b-124">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5970b-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="5970b-125">Elemento ExpressionBinding para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5970b-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5970b-126">Elemento de controle para controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="5970b-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="5970b-127">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5970b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
