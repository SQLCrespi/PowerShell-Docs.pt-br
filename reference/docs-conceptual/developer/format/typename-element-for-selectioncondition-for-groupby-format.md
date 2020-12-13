---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para SelectionCondition para GroupBy (formato)
description: Elemento TypeName para SelectionCondition para GroupBy (formato)
ms.openlocfilehash: 096d2355e113a7e44cc6ae31ea23efc3f01080a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664631"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="634c6-103">Elemento TypeName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="634c6-103">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="634c6-104">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="634c6-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="634c6-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="634c6-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="634c6-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento de EntrySelectedBy GroupBy (Format) para CustomEntry para o elemento GroupBy (Format) SelectionCondition para EntrySelectedBy para o elemento TypeName (Format) do SelectionCondition para GroupBy (</span><span class="sxs-lookup"><span data-stu-id="634c6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="634c6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="634c6-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="634c6-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="634c6-108">Attributes and Elements</span></span>

<span data-ttu-id="634c6-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="634c6-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="634c6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="634c6-110">Attributes</span></span>

<span data-ttu-id="634c6-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="634c6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="634c6-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="634c6-112">Child Elements</span></span>

<span data-ttu-id="634c6-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="634c6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="634c6-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="634c6-114">Parent Elements</span></span>

|<span data-ttu-id="634c6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="634c6-115">Element</span></span>|<span data-ttu-id="634c6-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="634c6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="634c6-117">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="634c6-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="634c6-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="634c6-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="634c6-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="634c6-119">Text Value</span></span>

<span data-ttu-id="634c6-120">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="634c6-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="634c6-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="634c6-121">Remarks</span></span>

<span data-ttu-id="634c6-122">Quando esse elemento é especificado, você não pode especificar o `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="634c6-122">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="634c6-123">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="634c6-123">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="634c6-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="634c6-124">See Also</span></span>

[<span data-ttu-id="634c6-125">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="634c6-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="634c6-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="634c6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
