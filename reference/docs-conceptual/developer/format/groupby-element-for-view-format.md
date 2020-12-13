---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento GroupBy para View (formato)
description: Elemento GroupBy para View (formato)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652095"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="014f2-103">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-103">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="014f2-104">Define como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="014f2-104">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="014f2-105">Esse elemento é usado ao definir uma tabela, lista, largura ou exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="014f2-105">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="014f2-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format)</span><span class="sxs-lookup"><span data-stu-id="014f2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="014f2-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="014f2-107">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="014f2-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="014f2-108">Attributes and Elements</span></span>

<span data-ttu-id="014f2-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="014f2-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="014f2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="014f2-110">Attributes</span></span>

<span data-ttu-id="014f2-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="014f2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="014f2-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="014f2-112">Child Elements</span></span>

|<span data-ttu-id="014f2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="014f2-113">Element</span></span>|<span data-ttu-id="014f2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="014f2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="014f2-115">Elemento CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-115">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="014f2-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="014f2-116">Optional element.</span></span><br /><br /> <span data-ttu-id="014f2-117">Define o controle personalizado que exibe novos grupos.</span><span class="sxs-lookup"><span data-stu-id="014f2-117">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="014f2-118">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-118">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="014f2-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="014f2-119">Optional element.</span></span><br /><br /> <span data-ttu-id="014f2-120">Especifica o nome de um controle usado para exibir o novo grupo.</span><span class="sxs-lookup"><span data-stu-id="014f2-120">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="014f2-121">Elemento Label para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-121">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="014f2-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="014f2-122">Optional element.</span></span><br /><br /> <span data-ttu-id="014f2-123">Especifica um rótulo que é exibido quando um novo grupo é encontrado.</span><span class="sxs-lookup"><span data-stu-id="014f2-123">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="014f2-124">Elemento PropertyName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-124">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="014f2-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="014f2-125">Optional element.</span></span><br /><br /> <span data-ttu-id="014f2-126">Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="014f2-126">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="014f2-127">Elemento ScriptBlock para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="014f2-128">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="014f2-128">Optional element.</span></span><br /><br /> <span data-ttu-id="014f2-129">Especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="014f2-129">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="014f2-130">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="014f2-130">Parent Elements</span></span>

|<span data-ttu-id="014f2-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="014f2-131">Element</span></span>|<span data-ttu-id="014f2-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="014f2-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="014f2-133">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-133">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="014f2-134">Define uma exibição que exibe um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="014f2-134">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="014f2-135">Comentários</span><span class="sxs-lookup"><span data-stu-id="014f2-135">Remarks</span></span>

<span data-ttu-id="014f2-136">Ao definir como um novo grupo de objetos é exibido, você deve especificar a propriedade ou o script que iniciará o novo grupo; no entanto, você não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="014f2-136">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="014f2-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="014f2-137">See Also</span></span>

[<span data-ttu-id="014f2-138">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-138">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="014f2-139">Elemento Label para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-139">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="014f2-140">Elemento PropertyName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-140">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="014f2-141">Elemento ScriptBlock para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-141">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="014f2-142">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="014f2-142">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="014f2-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="014f2-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
