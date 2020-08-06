---
title: Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5021f665b994581f9ff982e13af922d7940ebf2b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783306"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="8f80b-102">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8f80b-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="8f80b-103">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="8f80b-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="8f80b-104">Quando esse tipo está presente, a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="8f80b-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="8f80b-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy para WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8f80b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8f80b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8f80b-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8f80b-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8f80b-107">Attributes and Elements</span></span>

<span data-ttu-id="8f80b-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="8f80b-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8f80b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="8f80b-109">Attributes</span></span>

<span data-ttu-id="8f80b-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8f80b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8f80b-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="8f80b-111">Child Elements</span></span>

<span data-ttu-id="8f80b-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8f80b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8f80b-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="8f80b-113">Parent Elements</span></span>

|<span data-ttu-id="8f80b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f80b-114">Element</span></span>|<span data-ttu-id="8f80b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="8f80b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f80b-116">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8f80b-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="8f80b-117">Define a condição que deve existir para que essa entrada ampla seja usada.</span><span class="sxs-lookup"><span data-stu-id="8f80b-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8f80b-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="8f80b-118">Text Value</span></span>

<span data-ttu-id="8f80b-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="8f80b-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f80b-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="8f80b-120">Remarks</span></span>

<span data-ttu-id="8f80b-121">A condição de seleção pode especificar um tipo .NET ou um conjunto de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="8f80b-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="8f80b-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8f80b-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8f80b-123">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="8f80b-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f80b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f80b-124">See Also</span></span>

[<span data-ttu-id="8f80b-125">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="8f80b-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="8f80b-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="8f80b-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8f80b-127">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8f80b-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="8f80b-128">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="8f80b-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="8f80b-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f80b-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
