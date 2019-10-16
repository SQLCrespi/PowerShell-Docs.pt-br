---
title: Elemento Control para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369005"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="66961-102">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="66961-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="66961-103">Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="66961-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="66961-104">Elemento de configuração (Format) controla o elemento de configuração (formato) elemento de controle para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="66961-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="66961-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="66961-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="66961-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="66961-106">Attributes and Elements</span></span>

<span data-ttu-id="66961-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Control`.</span><span class="sxs-lookup"><span data-stu-id="66961-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="66961-108">Você deve especificar apenas um de cada elemento filho.</span><span class="sxs-lookup"><span data-stu-id="66961-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="66961-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="66961-109">Attributes</span></span>

<span data-ttu-id="66961-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66961-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="66961-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="66961-111">Child Elements</span></span>

|<span data-ttu-id="66961-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="66961-112">Element</span></span>|<span data-ttu-id="66961-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="66961-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="66961-114">Elemento CustomControl para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="66961-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="66961-115">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="66961-115">Required element.</span></span><br /><br /> <span data-ttu-id="66961-116">Define o controle.</span><span class="sxs-lookup"><span data-stu-id="66961-116">Defines the control.</span></span>|
|[<span data-ttu-id="66961-117">Elemento Name para controle de configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="66961-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="66961-118">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="66961-118">Required element.</span></span><br /><br /> <span data-ttu-id="66961-119">Especifica o nome usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="66961-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="66961-120">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="66961-120">Parent Elements</span></span>

|<span data-ttu-id="66961-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="66961-121">Element</span></span>|<span data-ttu-id="66961-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="66961-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="66961-123">Controla o elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="66961-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="66961-124">Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação ou por outros controles.</span><span class="sxs-lookup"><span data-stu-id="66961-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="66961-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="66961-125">Remarks</span></span>

<span data-ttu-id="66961-126">O nome fornecido a este controle pode ser referenciado nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="66961-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="66961-127">Elemento ExpressionBinding para CustomItem (Format)</span><span class="sxs-lookup"><span data-stu-id="66961-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="66961-128">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="66961-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="66961-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66961-129">See Also</span></span>

[<span data-ttu-id="66961-130">Controla o elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="66961-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="66961-131">Elemento CustomControl para controle de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="66961-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="66961-132">Elemento ExpressionBinding para CustomItem (Format)</span><span class="sxs-lookup"><span data-stu-id="66961-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="66961-133">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="66961-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="66961-134">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="66961-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="66961-135">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="66961-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
