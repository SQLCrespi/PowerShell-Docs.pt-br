---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para SelectionCondition para EntrySelectedBy para ListControl (formato)
description: Elemento TypeName para SelectionCondition para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: 2e8246e3ef2cba38824d8f8004acfffc3236df13
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645564"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="dcd90-103">Elemento TypeName para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dcd90-103">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="dcd90-104">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="dcd90-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="dcd90-105">Quando esse tipo está presente, a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="dcd90-105">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="dcd90-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) EntrySelectedBy para ListEntry para SelectionCondition para ListControl (Format) EntrySelectedBy Element for SelectionCondition for ListControl (Format) TypeName Element for EntrySelectedBy for para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="dcd90-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dcd90-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dcd90-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dcd90-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="dcd90-108">Attributes and Elements</span></span>

<span data-ttu-id="dcd90-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="dcd90-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dcd90-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="dcd90-110">Attributes</span></span>

<span data-ttu-id="dcd90-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="dcd90-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dcd90-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="dcd90-112">Child Elements</span></span>

<span data-ttu-id="dcd90-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="dcd90-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dcd90-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="dcd90-114">Parent Elements</span></span>

|<span data-ttu-id="dcd90-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="dcd90-115">Element</span></span>|<span data-ttu-id="dcd90-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="dcd90-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dcd90-117">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dcd90-117">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="dcd90-118">Define a condição que deve existir para que essa entrada de lista seja usada.</span><span class="sxs-lookup"><span data-stu-id="dcd90-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dcd90-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="dcd90-119">Text Value</span></span>

<span data-ttu-id="dcd90-120">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="dcd90-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dcd90-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="dcd90-121">Remarks</span></span>

<span data-ttu-id="dcd90-122">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="dcd90-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="dcd90-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="dcd90-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="dcd90-124">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="dcd90-124">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dcd90-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dcd90-125">See Also</span></span>

[<span data-ttu-id="dcd90-126">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="dcd90-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="dcd90-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="dcd90-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="dcd90-128">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="dcd90-128">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="dcd90-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcd90-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
