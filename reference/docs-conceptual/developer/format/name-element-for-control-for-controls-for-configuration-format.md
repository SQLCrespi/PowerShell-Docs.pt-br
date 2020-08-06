---
title: Elemento Name para controle de controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d45ba98b909ebee18e01d2b6985a48906ce39d9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783527"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="2e139-102">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2e139-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2e139-103">Especifica o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="2e139-103">Specifies the name of the control.</span></span> <span data-ttu-id="2e139-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="2e139-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2e139-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de nome de configuração (formato) para controle para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="2e139-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2e139-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2e139-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2e139-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2e139-107">Attributes and Elements</span></span>

<span data-ttu-id="2e139-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.</span><span class="sxs-lookup"><span data-stu-id="2e139-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2e139-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="2e139-109">Attributes</span></span>

<span data-ttu-id="2e139-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2e139-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2e139-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2e139-111">Child Elements</span></span>

<span data-ttu-id="2e139-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2e139-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2e139-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2e139-113">Parent Elements</span></span>

|<span data-ttu-id="2e139-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e139-114">Element</span></span>|<span data-ttu-id="2e139-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e139-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2e139-116">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2e139-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="2e139-117">Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="2e139-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2e139-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2e139-118">Text Value</span></span>

<span data-ttu-id="2e139-119">Especifique o nome que é usado para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="2e139-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e139-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="2e139-120">Remarks</span></span>

<span data-ttu-id="2e139-121">O nome especificado aqui pode ser usado nos seguintes elementos para fazer referência a esse controle.</span><span class="sxs-lookup"><span data-stu-id="2e139-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="2e139-122">Ao criar uma tabela, lista, exibição de controle largo ou personalizada, o controle pode ser especificado pelo seguinte elemento: [elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="2e139-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="2e139-123">Ao criar outro controle comum, esse controle pode ser especificado pelo seguinte elemento: [ExpressionBinding elemento para CustomItem para controles para configuração (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="2e139-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="2e139-124">Ao criar um controle que pode ser usado por um modo de exibição, esse controle pode ser especificado pelo seguinte elemento: [elemento ExpressionBinding para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="2e139-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="2e139-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e139-125">See Also</span></span>

[<span data-ttu-id="2e139-126">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2e139-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="2e139-127">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="2e139-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="2e139-128">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2e139-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="2e139-129">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="2e139-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="2e139-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e139-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
