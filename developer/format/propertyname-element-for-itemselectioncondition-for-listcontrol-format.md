---
title: Elemento PropertyName para ItemSelectionCondition para ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e707ae-3c84-4ceb-ba31-56b3ffde6d6c
caps.latest.revision: 7
ms.openlocfilehash: b15e26e18126f69eee7c3a857f9a461d4bdf5848
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064740"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="01c2b-102">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="01c2b-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="01c2b-103">Especifica a propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="01c2b-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="01c2b-104">Quando essa propriedade estiver presente ou quando ela é avaliada como `true`, a condição é atendida e o modo de exibição é usado.</span><span class="sxs-lookup"><span data-stu-id="01c2b-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="01c2b-105">Esse elemento é usado ao definir uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="01c2b-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="01c2b-106">Elemento (formato) elemento ViewDefinitions (formato) exibição elemento (formato) ListControl elemento (formato) ListEntries elemento (formato) ListEntry elemento de configuração para elemento de ListItems ListControl (formato) ListEntry para ListItem ListControl (formato) Elemento para ListItems para ListControl (formato) ItemSelectionCondition elemento ListItem para elemento de PropertyName ListControls ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="01c2b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="01c2b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="01c2b-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="01c2b-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="01c2b-108">Attributes and Elements</span></span>

<span data-ttu-id="01c2b-109">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="01c2b-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="01c2b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="01c2b-110">Attributes</span></span>

<span data-ttu-id="01c2b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="01c2b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="01c2b-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="01c2b-112">Child Elements</span></span>

<span data-ttu-id="01c2b-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="01c2b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="01c2b-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="01c2b-114">Parent Elements</span></span>

|<span data-ttu-id="01c2b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="01c2b-115">Element</span></span>|<span data-ttu-id="01c2b-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="01c2b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="01c2b-117">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="01c2b-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="01c2b-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="01c2b-118">Text Value</span></span>

<span data-ttu-id="01c2b-119">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="01c2b-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="01c2b-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="01c2b-120">Remarks</span></span>

<span data-ttu-id="01c2b-121">Se esse elemento é usado, não é possível especificar o [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) elemento ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="01c2b-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="01c2b-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01c2b-122">See Also</span></span>

[<span data-ttu-id="01c2b-123">Elemento ScriptBlock para ItemSelectionCondition para ListIControl (formato)</span><span class="sxs-lookup"><span data-stu-id="01c2b-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="01c2b-124">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="01c2b-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="01c2b-125">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="01c2b-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
