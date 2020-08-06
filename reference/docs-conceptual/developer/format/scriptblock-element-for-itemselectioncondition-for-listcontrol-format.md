---
title: Elemento ScriptBlock para ItemSelectionCondition para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 38dc952bfadd6aed24bae8cbef05adcd22e61dd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787624"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="25123-102">Elemento ScriptBlock para ItemSelectionCondition para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="25123-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="25123-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="25123-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="25123-104">Quando esse script é avaliado como `true` , a condição é atendida e o item de lista é usado.</span><span class="sxs-lookup"><span data-stu-id="25123-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="25123-105">Esse elemento é usado ao definir um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="25123-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="25123-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem de ListItems do elemento de controle de lista (Format) ItemSelectionCondition para o elemento de ListItem para ListControl (Format) para ItemSelectionCondition para</span><span class="sxs-lookup"><span data-stu-id="25123-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="25123-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="25123-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="25123-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="25123-108">Attributes and Elements</span></span>

<span data-ttu-id="25123-109">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="25123-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="25123-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="25123-110">Attributes</span></span>

<span data-ttu-id="25123-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25123-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="25123-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="25123-112">Child Elements</span></span>

<span data-ttu-id="25123-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25123-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="25123-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="25123-114">Parent Elements</span></span>

|<span data-ttu-id="25123-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="25123-115">Element</span></span>|<span data-ttu-id="25123-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="25123-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25123-117">Elemento ItemSelectionCondition para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="25123-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="25123-118">Define a condição que deve existir para este item de lista ser usado.</span><span class="sxs-lookup"><span data-stu-id="25123-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="25123-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="25123-119">Text Value</span></span>

<span data-ttu-id="25123-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="25123-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="25123-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="25123-121">Remarks</span></span>

<span data-ttu-id="25123-122">Se esse elemento for usado, você não poderá especificar o `PropertyName` elemento ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="25123-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="25123-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25123-123">See Also</span></span>

[<span data-ttu-id="25123-124">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="25123-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
