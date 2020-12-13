---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para ItemSelectionCondition para ListControl (formato)
description: Elemento PropertyName para ItemSelectionCondition para ListControl (formato)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665984"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="46d40-103">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="46d40-103">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="46d40-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="46d40-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="46d40-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a exibição é usada.</span><span class="sxs-lookup"><span data-stu-id="46d40-105">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="46d40-106">Esse elemento é usado ao definir um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="46d40-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="46d40-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format) o elemento ListEntry do elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem de ListItems para o elemento ListControl (Format) ItemSelectionCondition para ListItem for ListControls PropertyName Element para ItemSelectionCondition para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="46d40-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46d40-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="46d40-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46d40-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="46d40-109">Attributes and Elements</span></span>

<span data-ttu-id="46d40-110">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="46d40-110">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46d40-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="46d40-111">Attributes</span></span>

<span data-ttu-id="46d40-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="46d40-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46d40-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="46d40-113">Child Elements</span></span>

<span data-ttu-id="46d40-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="46d40-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="46d40-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="46d40-115">Parent Elements</span></span>

|<span data-ttu-id="46d40-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="46d40-116">Element</span></span>|<span data-ttu-id="46d40-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="46d40-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46d40-118">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="46d40-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="46d40-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="46d40-119">Text Value</span></span>

<span data-ttu-id="46d40-120">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="46d40-120">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="46d40-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="46d40-121">Remarks</span></span>

<span data-ttu-id="46d40-122">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="46d40-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="46d40-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46d40-123">See Also</span></span>

[<span data-ttu-id="46d40-124">Elemento ScriptBlock para ItemSelectionCondition para ListIControl (Format)</span><span class="sxs-lookup"><span data-stu-id="46d40-124">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="46d40-125">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="46d40-125">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="46d40-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="46d40-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
