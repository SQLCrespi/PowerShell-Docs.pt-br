---
title: Elemento Name para controle de controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365095"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="e6fb1-102">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="e6fb1-103">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="e6fb1-103">Specifies the name of the control.</span></span>

<span data-ttu-id="e6fb1-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format) Name Element para Control para View (Format)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e6fb1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6fb1-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e6fb1-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e6fb1-106">Attributes and Elements</span></span>

<span data-ttu-id="e6fb1-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Name`.</span><span class="sxs-lookup"><span data-stu-id="e6fb1-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e6fb1-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6fb1-108">Attributes</span></span>

<span data-ttu-id="e6fb1-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e6fb1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e6fb1-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="e6fb1-110">Child Elements</span></span>

<span data-ttu-id="e6fb1-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e6fb1-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e6fb1-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="e6fb1-112">Parent Elements</span></span>

|<span data-ttu-id="e6fb1-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6fb1-113">Element</span></span>|<span data-ttu-id="e6fb1-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6fb1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e6fb1-115">Elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="e6fb1-116">Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="e6fb1-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e6fb1-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="e6fb1-117">Text Value</span></span>

<span data-ttu-id="e6fb1-118">Especifique o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="e6fb1-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6fb1-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6fb1-119">Remarks</span></span>

<span data-ttu-id="e6fb1-120">O nome especificado aqui pode ser usado nos seguintes elementos para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="e6fb1-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="e6fb1-121">Ao criar uma tabela, lista, exibição de controle largo ou personalizada, o controle pode ser especificado pelo seguinte elemento: [elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="e6fb1-122">Ao criar outro controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo seguinte elemento: [ExpressionBinding elemento para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="e6fb1-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6fb1-123">See Also</span></span>

[<span data-ttu-id="e6fb1-124">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e6fb1-125">Elemento ExpressionBinding para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="e6fb1-126">Elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="e6fb1-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="e6fb1-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6fb1-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
