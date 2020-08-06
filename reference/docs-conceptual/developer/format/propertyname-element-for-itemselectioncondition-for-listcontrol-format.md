---
title: Elemento PropertyName para ItemSelectionCondition para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8bdbb05326f7ff5ccffa46215631a5c954080dc1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780858"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="9d5a0-102">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="9d5a0-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="9d5a0-104">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a exibição é usada.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="9d5a0-105">Esse elemento é usado ao definir um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="9d5a0-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format) o elemento ListEntry do elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem de ListItems para o elemento ListControl (Format) ItemSelectionCondition para ListItem for ListControls PropertyName Element para ItemSelectionCondition para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d5a0-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9d5a0-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d5a0-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9d5a0-108">Attributes and Elements</span></span>

<span data-ttu-id="9d5a0-109">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d5a0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9d5a0-110">Attributes</span></span>

<span data-ttu-id="9d5a0-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d5a0-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9d5a0-112">Child Elements</span></span>

<span data-ttu-id="9d5a0-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d5a0-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9d5a0-114">Parent Elements</span></span>

|<span data-ttu-id="9d5a0-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d5a0-115">Element</span></span>|<span data-ttu-id="9d5a0-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d5a0-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d5a0-117">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="9d5a0-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9d5a0-118">Text Value</span></span>

<span data-ttu-id="9d5a0-119">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d5a0-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="9d5a0-120">Remarks</span></span>

<span data-ttu-id="9d5a0-121">Se esse elemento for usado, você não poderá especificar o elemento [scriptblock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="9d5a0-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d5a0-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d5a0-122">See Also</span></span>

[<span data-ttu-id="9d5a0-123">Elemento ScriptBlock para ItemSelectionCondition para ListIControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="9d5a0-124">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9d5a0-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="9d5a0-125">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d5a0-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
