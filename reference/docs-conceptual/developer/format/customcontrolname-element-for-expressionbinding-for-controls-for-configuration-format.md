---
title: Elemento CustomControlName para ExpressionBinding para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5242935-2782-4d23-84f5-2446b2b7ba83
caps.latest.revision: 8
ms.openlocfilehash: c9abd9f22907b87323c16d603a9f75bb3d375a03
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364115"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="3e883-102">Elemento CustomControlName para ExpressionBinding para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="3e883-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="3e883-103">Especifica o nome de um controle comum.</span><span class="sxs-lookup"><span data-stu-id="3e883-103">Specifies the name of a common control.</span></span> <span data-ttu-id="3e883-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="3e883-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="3e883-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento Configuration (Format) CustomItem para CustomEntry para controles para o elemento ExpressionBinding de configuração para CustomItem para controles para a configuração (Format) CustomControlName Elemento para ExpressionBinding para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="3e883-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3e883-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3e883-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3e883-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3e883-107">Attributes and Elements</span></span>

<span data-ttu-id="3e883-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomControlName`.</span><span class="sxs-lookup"><span data-stu-id="3e883-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3e883-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3e883-109">Attributes</span></span>

<span data-ttu-id="3e883-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3e883-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3e883-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="3e883-111">Child Elements</span></span>

<span data-ttu-id="3e883-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3e883-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3e883-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="3e883-113">Parent Elements</span></span>

|<span data-ttu-id="3e883-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e883-114">Element</span></span>|<span data-ttu-id="3e883-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e883-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3e883-116">Elemento ExpressionBinding para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="3e883-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="3e883-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="3e883-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3e883-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="3e883-118">Text Value</span></span>

<span data-ttu-id="3e883-119">Especifique o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="3e883-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e883-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="3e883-120">Remarks</span></span>

<span data-ttu-id="3e883-121">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="3e883-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="3e883-122">Os seguintes elementos especificam os nomes desses controles:</span><span class="sxs-lookup"><span data-stu-id="3e883-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="3e883-123">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="3e883-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="3e883-124">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="3e883-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="3e883-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3e883-125">See Also</span></span>

[<span data-ttu-id="3e883-126">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="3e883-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="3e883-127">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="3e883-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="3e883-128">Elemento ExpressionBinding para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="3e883-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="3e883-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e883-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
