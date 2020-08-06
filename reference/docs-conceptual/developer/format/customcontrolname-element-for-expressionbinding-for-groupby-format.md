---
title: Elemento CustomControlName para ExpressionBinding para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 06e612b25accf81467108ca48500943153efd575
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785992"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="12974-102">Elemento CustomControlName para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12974-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="12974-103">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="12974-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="12974-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="12974-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="12974-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento de GroupBy (Format) CustomEntry para CustomControl para o elemento de CustomItem GroupBy (Format) para CustomEntry para o elemento ExpressionBinding de GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="12974-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="12974-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="12974-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12974-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="12974-107">Attributes and Elements</span></span>

<span data-ttu-id="12974-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlName` elemento.</span><span class="sxs-lookup"><span data-stu-id="12974-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="12974-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="12974-109">Attributes</span></span>

<span data-ttu-id="12974-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="12974-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="12974-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="12974-111">Child Elements</span></span>

<span data-ttu-id="12974-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="12974-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="12974-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="12974-113">Parent Elements</span></span>

|<span data-ttu-id="12974-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="12974-114">Element</span></span>|<span data-ttu-id="12974-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="12974-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12974-116">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12974-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="12974-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="12974-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="12974-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="12974-118">Text Value</span></span>

<span data-ttu-id="12974-119">Especifique o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="12974-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="12974-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="12974-120">Remarks</span></span>

<span data-ttu-id="12974-121">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="12974-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="12974-122">Os seguintes elementos especificam os nomes desses controles:</span><span class="sxs-lookup"><span data-stu-id="12974-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="12974-123">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="12974-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="12974-124">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="12974-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="12974-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12974-125">See Also</span></span>

[<span data-ttu-id="12974-126">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="12974-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="12974-127">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="12974-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="12974-128">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12974-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="12974-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="12974-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
