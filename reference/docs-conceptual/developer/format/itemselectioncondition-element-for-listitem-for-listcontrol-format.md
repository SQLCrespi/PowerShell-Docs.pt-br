---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ItemSelectionCondition para ListItem para ListControl (formato)
description: Elemento ItemSelectionCondition para ListItem para ListControl (formato)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667803"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="a7349-103">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a7349-103">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="a7349-104">Define a condição que deve existir para este item de lista ser usado.</span><span class="sxs-lookup"><span data-stu-id="a7349-104">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="a7349-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem para ListItems para o elemento ListControl (Format) ItemSelectionCondition para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a7349-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a7349-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a7349-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a7349-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a7349-107">Attributes and Elements</span></span>

<span data-ttu-id="a7349-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="a7349-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a7349-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7349-109">Attributes</span></span>

<span data-ttu-id="a7349-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a7349-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a7349-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a7349-111">Child Elements</span></span>

|<span data-ttu-id="a7349-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7349-112">Element</span></span>|<span data-ttu-id="a7349-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="a7349-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7349-114">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a7349-114">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="a7349-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a7349-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a7349-116">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="a7349-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a7349-117">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a7349-117">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="a7349-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a7349-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a7349-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="a7349-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a7349-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a7349-120">Parent Elements</span></span>

|<span data-ttu-id="a7349-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7349-121">Element</span></span>|<span data-ttu-id="a7349-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="a7349-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7349-123">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a7349-123">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="a7349-124">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="a7349-124">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a7349-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="a7349-125">Remarks</span></span>

<span data-ttu-id="a7349-126">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a7349-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7349-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a7349-127">See Also</span></span>

[<span data-ttu-id="a7349-128">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a7349-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="a7349-129">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a7349-129">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="a7349-130">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a7349-130">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="a7349-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7349-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
