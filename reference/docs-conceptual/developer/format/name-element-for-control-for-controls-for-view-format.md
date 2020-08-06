---
title: Elemento Name para controle de controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 109f3a40606dbe82322decf0c69d2367c75175f6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781079"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="7fd19-102">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7fd19-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="7fd19-103">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="7fd19-103">Specifies the name of the control.</span></span>

<span data-ttu-id="7fd19-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para View (Format) Name Element para Control para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7fd19-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7fd19-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7fd19-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7fd19-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7fd19-106">Attributes and Elements</span></span>

<span data-ttu-id="7fd19-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.</span><span class="sxs-lookup"><span data-stu-id="7fd19-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7fd19-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7fd19-108">Attributes</span></span>

<span data-ttu-id="7fd19-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7fd19-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7fd19-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="7fd19-110">Child Elements</span></span>

<span data-ttu-id="7fd19-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7fd19-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7fd19-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="7fd19-112">Parent Elements</span></span>

|<span data-ttu-id="7fd19-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fd19-113">Element</span></span>|<span data-ttu-id="7fd19-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="7fd19-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7fd19-115">Elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7fd19-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="7fd19-116">Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="7fd19-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7fd19-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="7fd19-117">Text Value</span></span>

<span data-ttu-id="7fd19-118">Especifique o nome que é usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="7fd19-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="7fd19-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="7fd19-119">Remarks</span></span>

<span data-ttu-id="7fd19-120">O nome especificado aqui pode ser usado nos seguintes elementos para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="7fd19-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="7fd19-121">Ao criar uma tabela, lista, exibição de controle largo ou personalizada, o controle pode ser especificado pelo seguinte elemento: [elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="7fd19-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="7fd19-122">Ao criar outro controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo seguinte elemento: [ExpressionBinding elemento para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="7fd19-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="7fd19-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7fd19-123">See Also</span></span>

[<span data-ttu-id="7fd19-124">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7fd19-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="7fd19-125">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7fd19-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="7fd19-126">Elemento Control para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7fd19-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="7fd19-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fd19-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
