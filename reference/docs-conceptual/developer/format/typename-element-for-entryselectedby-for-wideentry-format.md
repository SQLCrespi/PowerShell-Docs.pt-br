---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para EntrySelectedBy para WideEntry (formato)
description: Elemento TypeName para EntrySelectedBy para WideEntry (formato)
ms.openlocfilehash: 2e0facd6ff7c6fec96dabf488449a8502429bcff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654788"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="a65d3-103">Elemento TypeName para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="a65d3-103">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="a65d3-104">Especifica um tipo .NET para a definição.</span><span class="sxs-lookup"><span data-stu-id="a65d3-104">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="a65d3-105">A definição é usada sempre que este objeto é exibido.</span><span class="sxs-lookup"><span data-stu-id="a65d3-105">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="a65d3-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) TypeName Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a65d3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a65d3-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a65d3-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a65d3-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a65d3-108">Attributes and Elements</span></span>

<span data-ttu-id="a65d3-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="a65d3-109">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a65d3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a65d3-110">Attributes</span></span>

<span data-ttu-id="a65d3-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a65d3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a65d3-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a65d3-112">Child Elements</span></span>

<span data-ttu-id="a65d3-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a65d3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a65d3-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a65d3-114">Parent Elements</span></span>

|<span data-ttu-id="a65d3-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a65d3-115">Element</span></span>|<span data-ttu-id="a65d3-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="a65d3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a65d3-117">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="a65d3-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="a65d3-118">Define os tipos .NET que usam essa entrada ampla ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="a65d3-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a65d3-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="a65d3-119">Text Value</span></span>

<span data-ttu-id="a65d3-120">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="a65d3-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a65d3-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="a65d3-121">Remarks</span></span>

<span data-ttu-id="a65d3-122">Cada entrada larga deve especificar um ou mais tipos .NET, um conjunto de seleção ou a condição de seleção que deve existir para a definição a ser usada.</span><span class="sxs-lookup"><span data-stu-id="a65d3-122">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="a65d3-123">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="a65d3-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a65d3-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a65d3-124">See Also</span></span>

[<span data-ttu-id="a65d3-125">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="a65d3-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a65d3-126">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="a65d3-126">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="a65d3-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65d3-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
