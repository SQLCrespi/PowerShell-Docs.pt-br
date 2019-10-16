---
title: Elemento CustomControlName para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368875"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="35ffe-102">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="35ffe-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="35ffe-103">Especifica o nome de um controle personalizado que é usado para exibir o novo grupo.</span><span class="sxs-lookup"><span data-stu-id="35ffe-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="35ffe-104">Esse elemento é usado ao definir uma tabela, lista, exibição de controle largo ou personalizada.</span><span class="sxs-lookup"><span data-stu-id="35ffe-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="35ffe-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControlName element de GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="35ffe-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="35ffe-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="35ffe-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="35ffe-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="35ffe-107">Attributes and Elements</span></span>

<span data-ttu-id="35ffe-108">As seções a seguir descrevem os atributos, os elementos filho e os elementos pai do elemento `CustomControlName`.</span><span class="sxs-lookup"><span data-stu-id="35ffe-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="35ffe-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="35ffe-109">Attributes</span></span>

<span data-ttu-id="35ffe-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="35ffe-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="35ffe-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="35ffe-111">Child Elements</span></span>

<span data-ttu-id="35ffe-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="35ffe-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="35ffe-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="35ffe-113">Parent Elements</span></span>

|<span data-ttu-id="35ffe-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="35ffe-114">Element</span></span>|<span data-ttu-id="35ffe-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="35ffe-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35ffe-116">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="35ffe-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="35ffe-117">Define como o Windows PowerShell exibe um novo grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="35ffe-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="35ffe-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="35ffe-118">Text Value</span></span>

<span data-ttu-id="35ffe-119">Especifique o nome do controle personalizado usado para exibir um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="35ffe-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="35ffe-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="35ffe-120">Remarks</span></span>

<span data-ttu-id="35ffe-121">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="35ffe-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="35ffe-122">Os seguintes elementos especificam os nomes desses controles personalizados:</span><span class="sxs-lookup"><span data-stu-id="35ffe-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="35ffe-123">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="35ffe-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="35ffe-124">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="35ffe-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="35ffe-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35ffe-125">See Also</span></span>

[<span data-ttu-id="35ffe-126">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="35ffe-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="35ffe-127">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="35ffe-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="35ffe-128">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="35ffe-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="35ffe-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="35ffe-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
