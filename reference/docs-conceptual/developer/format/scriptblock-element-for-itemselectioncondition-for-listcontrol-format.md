---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)
description: Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665063"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="f5f5e-103">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f5f5e-103">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="f5f5e-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f5f5e-105">Quando esse script é avaliado como `true` , a condição é atendida e o item de lista é usado.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-105">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="f5f5e-106">Esse elemento é usado ao definir um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="f5f5e-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem de ListItems do elemento de controle de lista (Format) ItemSelectionCondition para o elemento de ListItem para ListControl (Format) para ItemSelectionCondition para</span><span class="sxs-lookup"><span data-stu-id="f5f5e-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f5f5e-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f5f5e-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f5f5e-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f5f5e-109">Attributes and Elements</span></span>

<span data-ttu-id="f5f5e-110">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-110">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f5f5e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5f5e-111">Attributes</span></span>

<span data-ttu-id="f5f5e-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f5f5e-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f5f5e-113">Child Elements</span></span>

<span data-ttu-id="f5f5e-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f5f5e-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f5f5e-115">Parent Elements</span></span>

|<span data-ttu-id="f5f5e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5f5e-116">Element</span></span>|<span data-ttu-id="f5f5e-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5f5e-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f5f5e-118">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f5f5e-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="f5f5e-119">Define a condição que deve existir para este item de lista ser usado.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-119">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f5f5e-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f5f5e-120">Text Value</span></span>

<span data-ttu-id="f5f5e-121">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5f5e-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="f5f5e-122">Remarks</span></span>

<span data-ttu-id="f5f5e-123">Se esse elemento for usado, você não poderá especificar o `PropertyName` elemento ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-123">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5f5e-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5f5e-124">See Also</span></span>

[<span data-ttu-id="f5f5e-125">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5f5e-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
