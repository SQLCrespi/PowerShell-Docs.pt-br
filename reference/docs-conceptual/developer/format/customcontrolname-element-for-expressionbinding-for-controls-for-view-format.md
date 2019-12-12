---
title: Elemento CustomControlName para ExpressionBinding para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b6ee11e-9086-41d2-afd3-42fb9f24da69
caps.latest.revision: 7
ms.openlocfilehash: bf1d57447f9018f1535af14466427aaeabc048f3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369145"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="fdc0c-102">Elemento CustomControlName para ExpressionBinding para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-102">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="fdc0c-103">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="fdc0c-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="fdc0c-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding View (Format) para CustomItem para controles para View (Format) CustomControlName Elemento para ExpressionBindine para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fdc0c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fdc0c-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fdc0c-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fdc0c-107">Attributes and Elements</span></span>

<span data-ttu-id="fdc0c-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomControlName`.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fdc0c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fdc0c-109">Attributes</span></span>

<span data-ttu-id="fdc0c-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fdc0c-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="fdc0c-111">Child Elements</span></span>

<span data-ttu-id="fdc0c-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fdc0c-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="fdc0c-113">Parent Elements</span></span>

|<span data-ttu-id="fdc0c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdc0c-114">Element</span></span>|<span data-ttu-id="fdc0c-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="fdc0c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fdc0c-116">Elemento ExpressionBinding para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="fdc0c-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fdc0c-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="fdc0c-118">Text Value</span></span>

<span data-ttu-id="fdc0c-119">Especifique o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdc0c-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="fdc0c-120">Remarks</span></span>

<span data-ttu-id="fdc0c-121">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="fdc0c-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="fdc0c-122">Os seguintes elementos especificam os nomes desses controles:</span><span class="sxs-lookup"><span data-stu-id="fdc0c-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="fdc0c-123">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="fdc0c-124">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="fdc0c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fdc0c-125">See Also</span></span>

[<span data-ttu-id="fdc0c-126">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="fdc0c-127">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="fdc0c-128">Elemento ExpressionBinding para CustomItem para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="fdc0c-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="fdc0c-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdc0c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
