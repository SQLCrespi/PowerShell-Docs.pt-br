---
title: Elemento CustomControlName para ExpressionBinding para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 690b6ae01b8116b72fbd00aef574feda1fd737b0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786026"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="86068-102">Elemento CustomControlName para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="86068-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="86068-103">Especifica o nome de um controle comum.</span><span class="sxs-lookup"><span data-stu-id="86068-103">Specifies the name of a common control.</span></span> <span data-ttu-id="86068-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="86068-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="86068-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para o elemento Configuration (Format) CustomControlName para ExpressionBinding para controles para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="86068-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="86068-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="86068-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="86068-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="86068-107">Attributes and Elements</span></span>

<span data-ttu-id="86068-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlName` elemento.</span><span class="sxs-lookup"><span data-stu-id="86068-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="86068-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="86068-109">Attributes</span></span>

<span data-ttu-id="86068-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="86068-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="86068-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="86068-111">Child Elements</span></span>

<span data-ttu-id="86068-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="86068-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="86068-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="86068-113">Parent Elements</span></span>

|<span data-ttu-id="86068-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="86068-114">Element</span></span>|<span data-ttu-id="86068-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="86068-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86068-116">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="86068-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="86068-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="86068-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="86068-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="86068-118">Text Value</span></span>

<span data-ttu-id="86068-119">Especifique o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="86068-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="86068-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="86068-120">Remarks</span></span>

<span data-ttu-id="86068-121">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="86068-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="86068-122">Os seguintes elementos especificam os nomes desses controles:</span><span class="sxs-lookup"><span data-stu-id="86068-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="86068-123">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="86068-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="86068-124">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="86068-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="86068-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86068-125">See Also</span></span>

[<span data-ttu-id="86068-126">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="86068-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="86068-127">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="86068-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="86068-128">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="86068-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="86068-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="86068-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
