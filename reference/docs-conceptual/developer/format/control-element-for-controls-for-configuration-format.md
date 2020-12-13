---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Control para Controls para Configuration (formato)
description: Elemento Control para Controls para Configuration (formato)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655655"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="0df7f-103">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-103">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="0df7f-104">Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.</span><span class="sxs-lookup"><span data-stu-id="0df7f-104">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="0df7f-105">Elemento de configuração (Format) controla o elemento de configuração (formato) elemento de controle para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0df7f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0df7f-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0df7f-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0df7f-107">Attributes and Elements</span></span>

<span data-ttu-id="0df7f-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Control` elemento.</span><span class="sxs-lookup"><span data-stu-id="0df7f-108">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="0df7f-109">Você deve especificar apenas um de cada elemento filho.</span><span class="sxs-lookup"><span data-stu-id="0df7f-109">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0df7f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0df7f-110">Attributes</span></span>

<span data-ttu-id="0df7f-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0df7f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0df7f-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0df7f-112">Child Elements</span></span>

|<span data-ttu-id="0df7f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0df7f-113">Element</span></span>|<span data-ttu-id="0df7f-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="0df7f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0df7f-115">Elemento CustomControl para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-115">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="0df7f-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="0df7f-116">Required element.</span></span><br /><br /> <span data-ttu-id="0df7f-117">Define o controle.</span><span class="sxs-lookup"><span data-stu-id="0df7f-117">Defines the control.</span></span>|
|[<span data-ttu-id="0df7f-118">Elemento Name para controle de configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="0df7f-118">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="0df7f-119">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="0df7f-119">Required element.</span></span><br /><br /> <span data-ttu-id="0df7f-120">Especifica o nome usado para referenciar o controle.</span><span class="sxs-lookup"><span data-stu-id="0df7f-120">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0df7f-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0df7f-121">Parent Elements</span></span>

|<span data-ttu-id="0df7f-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="0df7f-122">Element</span></span>|<span data-ttu-id="0df7f-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="0df7f-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0df7f-124">Controla o elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-124">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="0df7f-125">Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação ou por outros controles.</span><span class="sxs-lookup"><span data-stu-id="0df7f-125">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0df7f-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="0df7f-126">Remarks</span></span>

<span data-ttu-id="0df7f-127">O nome fornecido a este controle pode ser referenciado nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="0df7f-127">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="0df7f-128">Elemento ExpressionBinding para CustomItem (Format)</span><span class="sxs-lookup"><span data-stu-id="0df7f-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="0df7f-129">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-129">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="0df7f-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0df7f-130">See Also</span></span>

[<span data-ttu-id="0df7f-131">Controla o elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-131">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="0df7f-132">Elemento CustomControl para controle de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-132">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="0df7f-133">Elemento ExpressionBinding para CustomItem (Format)</span><span class="sxs-lookup"><span data-stu-id="0df7f-133">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="0df7f-134">Elemento GroupBy para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-134">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="0df7f-135">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0df7f-135">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="0df7f-136">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0df7f-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
