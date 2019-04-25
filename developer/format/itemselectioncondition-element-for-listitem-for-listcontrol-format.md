---
title: Elemento ItemSelectionCondition para ListItem para ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065437"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="9dbdd-102">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="9dbdd-103">Define a condição que deve existir para esse item de lista a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="9dbdd-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento ListControl elemento (formato) ListEntries elemento de configuração para ListControl (formato) elemento ListEntry ListEntries para elemento de ListItems ListControl (formato) ListEntry para elemento ListItem ListControl (formato) ListItems para ListControl (formato) ItemSelectionCondition elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9dbdd-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9dbdd-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9dbdd-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="9dbdd-106">Attributes and Elements</span></span>

<span data-ttu-id="9dbdd-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9dbdd-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9dbdd-108">Attributes</span></span>

<span data-ttu-id="9dbdd-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9dbdd-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9dbdd-110">Child Elements</span></span>

|<span data-ttu-id="9dbdd-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="9dbdd-111">Element</span></span>|<span data-ttu-id="9dbdd-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9dbdd-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9dbdd-113">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="9dbdd-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-114">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbdd-115">Especifica a propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="9dbdd-116">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="9dbdd-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-117">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbdd-118">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9dbdd-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9dbdd-119">Parent Elements</span></span>

|<span data-ttu-id="9dbdd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9dbdd-120">Element</span></span>|<span data-ttu-id="9dbdd-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="9dbdd-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9dbdd-122">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="9dbdd-123">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9dbdd-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="9dbdd-124">Remarks</span></span>

<span data-ttu-id="9dbdd-125">Você pode especificar um nome de propriedade ou um script para essa condição, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="9dbdd-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="9dbdd-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9dbdd-126">See Also</span></span>

[<span data-ttu-id="9dbdd-127">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="9dbdd-128">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="9dbdd-129">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9dbdd-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="9dbdd-130">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dbdd-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
