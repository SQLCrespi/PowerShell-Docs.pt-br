---
title: Elemento TypeName para SelectionCondition para EntrySelectedBy para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bc58d630e65b316f9223bf3c529f928358e38ebc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787362"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="e660d-102">Elemento TypeName para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e660d-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="e660d-103">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="e660d-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="e660d-104">Quando esse tipo está presente, a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="e660d-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="e660d-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) EntrySelectedBy para ListEntry para SelectionCondition para ListControl (Format) EntrySelectedBy Element for SelectionCondition for ListControl (Format) TypeName Element for EntrySelectedBy for para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e660d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e660d-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e660d-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e660d-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e660d-107">Attributes and Elements</span></span>

<span data-ttu-id="e660d-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="e660d-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e660d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e660d-109">Attributes</span></span>

<span data-ttu-id="e660d-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e660d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e660d-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e660d-111">Child Elements</span></span>

<span data-ttu-id="e660d-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e660d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e660d-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e660d-113">Parent Elements</span></span>

|<span data-ttu-id="e660d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e660d-114">Element</span></span>|<span data-ttu-id="e660d-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="e660d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e660d-116">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e660d-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="e660d-117">Define a condição que deve existir para que essa entrada de lista seja usada.</span><span class="sxs-lookup"><span data-stu-id="e660d-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e660d-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="e660d-118">Text Value</span></span>

<span data-ttu-id="e660d-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="e660d-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e660d-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="e660d-120">Remarks</span></span>

<span data-ttu-id="e660d-121">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="e660d-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="e660d-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e660d-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e660d-123">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="e660d-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e660d-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e660d-124">See Also</span></span>

[<span data-ttu-id="e660d-125">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="e660d-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e660d-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="e660d-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e660d-127">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e660d-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="e660d-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e660d-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
