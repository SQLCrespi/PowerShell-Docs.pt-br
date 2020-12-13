---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para EntrySelectedBy para TableControl (formato)
description: Elemento TypeName para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: 5a9f5cda1810d461d19ffb48a1cfa2d41f87ca96
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651430"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="cda66-103">Elemento TypeName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="cda66-103">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="cda66-104">Especifica um tipo .NET que usa essa entrada da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="cda66-104">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="cda66-105">Não há nenhum limite para o número de tipos que podem ser especificados para uma entrada de tabela.</span><span class="sxs-lookup"><span data-stu-id="cda66-105">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="cda66-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="cda66-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cda66-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cda66-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cda66-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="cda66-108">Attributes and Elements</span></span>

<span data-ttu-id="cda66-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="cda66-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cda66-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="cda66-110">Attributes</span></span>

<span data-ttu-id="cda66-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="cda66-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cda66-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="cda66-112">Child Elements</span></span>

<span data-ttu-id="cda66-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="cda66-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cda66-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="cda66-114">Parent Elements</span></span>

|<span data-ttu-id="cda66-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cda66-115">Element</span></span>|<span data-ttu-id="cda66-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="cda66-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cda66-117">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cda66-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="cda66-118">Define os tipos .NET que usam essa entrada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="cda66-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cda66-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="cda66-119">Text Value</span></span>

<span data-ttu-id="cda66-120">Especifique o nome do tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="cda66-120">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="cda66-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="cda66-121">Remarks</span></span>

<span data-ttu-id="cda66-122">Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="cda66-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="cda66-123">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="cda66-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cda66-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cda66-124">See Also</span></span>

[<span data-ttu-id="cda66-125">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="cda66-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="cda66-126">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cda66-126">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="cda66-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cda66-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
