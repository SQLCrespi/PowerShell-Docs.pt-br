---
title: Elemento TypeName para EntrySelectedBy para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5e7b73db5aa597d96141454008c5c58b1827df24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780212"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="0b9ed-102">Elemento TypeName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="0b9ed-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="0b9ed-103">Especifica um tipo .NET que usa essa entrada da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="0b9ed-104">Não há nenhum limite para o número de tipos que podem ser especificados para uma entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="0b9ed-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries elemento (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="0b9ed-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0b9ed-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0b9ed-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b9ed-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0b9ed-107">Attributes and Elements</span></span>

<span data-ttu-id="0b9ed-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b9ed-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b9ed-109">Attributes</span></span>

<span data-ttu-id="0b9ed-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0b9ed-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0b9ed-111">Child Elements</span></span>

<span data-ttu-id="0b9ed-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0b9ed-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0b9ed-113">Parent Elements</span></span>

|<span data-ttu-id="0b9ed-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b9ed-114">Element</span></span>|<span data-ttu-id="0b9ed-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b9ed-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b9ed-116">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0b9ed-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="0b9ed-117">Define os tipos .NET que usam essa entrada de lista ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0b9ed-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0b9ed-118">Text Value</span></span>

<span data-ttu-id="0b9ed-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="0b9ed-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b9ed-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="0b9ed-120">Remarks</span></span>

<span data-ttu-id="0b9ed-121">Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="0b9ed-122">Para obter mais informações sobre como esse elemento é usado em um modo de exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="0b9ed-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="0b9ed-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0b9ed-123">Example</span></span>

<span data-ttu-id="0b9ed-124">O exemplo a seguir mostra como especificar um conjunto de seleção para uma entrada de uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="0b9ed-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0b9ed-125">See Also</span></span>

[<span data-ttu-id="0b9ed-126">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="0b9ed-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="0b9ed-127">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0b9ed-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="0b9ed-128">Elemento SelectionSetName para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0b9ed-128">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="0b9ed-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b9ed-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
