---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomControlName para ExpressionBinding para GroupBy (formato)
description: Elemento CustomControlName para ExpressionBinding para GroupBy (formato)
ms.openlocfilehash: bb7dbd449137628da1794628c5a7d7e10158dd46
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655432"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="0b2e7-103">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-103">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="0b2e7-104">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="0b2e7-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="0b2e7-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento de GroupBy (Format) CustomEntry para CustomControl para o elemento de CustomItem GroupBy (Format) para CustomEntry para o elemento ExpressionBinding de GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0b2e7-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0b2e7-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b2e7-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0b2e7-108">Attributes and Elements</span></span>

<span data-ttu-id="0b2e7-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlName` elemento.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b2e7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b2e7-110">Attributes</span></span>

<span data-ttu-id="0b2e7-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0b2e7-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0b2e7-112">Child Elements</span></span>

<span data-ttu-id="0b2e7-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0b2e7-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0b2e7-114">Parent Elements</span></span>

|<span data-ttu-id="0b2e7-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b2e7-115">Element</span></span>|<span data-ttu-id="0b2e7-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b2e7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b2e7-117">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-117">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="0b2e7-118">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0b2e7-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0b2e7-119">Text Value</span></span>

<span data-ttu-id="0b2e7-120">Especifique o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b2e7-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="0b2e7-121">Remarks</span></span>

<span data-ttu-id="0b2e7-122">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="0b2e7-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="0b2e7-123">Os seguintes elementos especificam os nomes desses controles:</span><span class="sxs-lookup"><span data-stu-id="0b2e7-123">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="0b2e7-124">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="0b2e7-125">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="0b2e7-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0b2e7-126">See Also</span></span>

[<span data-ttu-id="0b2e7-127">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="0b2e7-128">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="0b2e7-129">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0b2e7-129">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="0b2e7-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b2e7-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
