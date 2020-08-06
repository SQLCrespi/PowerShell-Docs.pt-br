---
title: Elemento PropertyName para SelectionCondition para controles para configuração (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7730951a840fcfcd8bf819fff5182049bd6b6c23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773123"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="b207e-102">Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="b207e-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b207e-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="b207e-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="b207e-104">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada é usada.</span><span class="sxs-lookup"><span data-stu-id="b207e-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="b207e-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="b207e-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b207e-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para CustomEntry para o elemento de configuração (Format) PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="b207e-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b207e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b207e-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b207e-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b207e-108">Attributes and Elements</span></span>

<span data-ttu-id="b207e-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="b207e-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b207e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b207e-110">Attributes</span></span>

<span data-ttu-id="b207e-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b207e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b207e-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b207e-112">Child Elements</span></span>

<span data-ttu-id="b207e-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b207e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b207e-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b207e-114">Parent Elements</span></span>

|<span data-ttu-id="b207e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b207e-115">Element</span></span>|<span data-ttu-id="b207e-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="b207e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b207e-117">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="b207e-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="b207e-118">Define uma condição que deve existir para que uma definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="b207e-118">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b207e-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b207e-119">Text Value</span></span>

<span data-ttu-id="b207e-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="b207e-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="b207e-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="b207e-121">Remarks</span></span>

<span data-ttu-id="b207e-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="b207e-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="b207e-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b207e-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b207e-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b207e-124">See Also</span></span>

[<span data-ttu-id="b207e-125">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="b207e-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="b207e-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b207e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
