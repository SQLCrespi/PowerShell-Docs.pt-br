---
title: Elemento ItemSelectionCondition para ListItem para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f5c388928668e03b96923130fb5849f637548f12
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783612"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="f097f-102">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f097f-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="f097f-103">Define a condição que deve existir para este item de lista ser usado.</span><span class="sxs-lookup"><span data-stu-id="f097f-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="f097f-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem para ListItems para o elemento ListControl (Format) ItemSelectionCondition para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f097f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f097f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f097f-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f097f-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f097f-106">Attributes and Elements</span></span>

<span data-ttu-id="f097f-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ItemSelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="f097f-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f097f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f097f-108">Attributes</span></span>

<span data-ttu-id="f097f-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f097f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f097f-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f097f-110">Child Elements</span></span>

|<span data-ttu-id="f097f-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f097f-111">Element</span></span>|<span data-ttu-id="f097f-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f097f-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f097f-113">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f097f-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="f097f-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f097f-114">Optional element.</span></span><br /><br /> <span data-ttu-id="f097f-115">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f097f-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f097f-116">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f097f-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="f097f-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f097f-117">Optional element.</span></span><br /><br /> <span data-ttu-id="f097f-118">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f097f-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f097f-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f097f-119">Parent Elements</span></span>

|<span data-ttu-id="f097f-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f097f-120">Element</span></span>|<span data-ttu-id="f097f-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="f097f-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f097f-122">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f097f-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="f097f-123">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="f097f-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f097f-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="f097f-124">Remarks</span></span>

<span data-ttu-id="f097f-125">Você pode especificar um nome de propriedade ou um script para essa condição, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="f097f-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="f097f-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f097f-126">See Also</span></span>

[<span data-ttu-id="f097f-127">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f097f-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="f097f-128">Elemento PropertyName para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f097f-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="f097f-129">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f097f-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="f097f-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f097f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
