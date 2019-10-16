---
title: Elemento PropertyName para SelectionCondition para controles para configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec048408-e1c6-41ef-b39b-72f4c2dcf2ac
caps.latest.revision: 6
ms.openlocfilehash: b4b2440fdb7171d09fdc16ac7cc4f25ed1a4bb78
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362395"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="f5c54-102">Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f5c54-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f5c54-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f5c54-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f5c54-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a entrada é usada.</span><span class="sxs-lookup"><span data-stu-id="f5c54-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="f5c54-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="f5c54-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f5c54-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para CustomEntry para a configuração ( Format) elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f5c54-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f5c54-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f5c54-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f5c54-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f5c54-108">Attributes and Elements</span></span>

<span data-ttu-id="f5c54-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="f5c54-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f5c54-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5c54-110">Attributes</span></span>

<span data-ttu-id="f5c54-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f5c54-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f5c54-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="f5c54-112">Child Elements</span></span>

<span data-ttu-id="f5c54-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f5c54-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f5c54-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="f5c54-114">Parent Elements</span></span>

|<span data-ttu-id="f5c54-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5c54-115">Element</span></span>|<span data-ttu-id="f5c54-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5c54-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f5c54-117">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="f5c54-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="f5c54-118">Define uma condição que deve existir para que uma definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="f5c54-118">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f5c54-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f5c54-119">Text Value</span></span>

<span data-ttu-id="f5c54-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="f5c54-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5c54-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="f5c54-121">Remarks</span></span>

<span data-ttu-id="f5c54-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="f5c54-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="f5c54-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f5c54-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5c54-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5c54-124">See Also</span></span>

[<span data-ttu-id="f5c54-125">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="f5c54-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="f5c54-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5c54-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
