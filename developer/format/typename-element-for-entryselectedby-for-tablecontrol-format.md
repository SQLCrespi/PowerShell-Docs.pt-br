---
title: Elemento TypeName para EntrySelectedBy para TableControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd872ada-d476-4c4d-a788-ccac3f983070
caps.latest.revision: 10
ms.openlocfilehash: 7bbb47268a23fcb37a34e2287a6ce949313a13bb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083953"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="bfce4-102">Elemento TypeName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bfce4-102">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="bfce4-103">Especifica um tipo .NET que usa essa entrada da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="bfce4-103">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="bfce4-104">Não há nenhum limite para o número de tipos que podem ser especificados para uma entrada de tabela.</span><span class="sxs-lookup"><span data-stu-id="bfce4-104">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="bfce4-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento TableControl (formato) elemento TableRowEntries (formato) elemento TableRowEntry (formato) elemento EntrySelectedBy (formato) TypeName elemento de configuração para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="bfce4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bfce4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bfce4-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bfce4-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="bfce4-107">Attributes and Elements</span></span>

<span data-ttu-id="bfce4-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="bfce4-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bfce4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="bfce4-109">Attributes</span></span>

<span data-ttu-id="bfce4-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bfce4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bfce4-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bfce4-111">Child Elements</span></span>

<span data-ttu-id="bfce4-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bfce4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bfce4-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bfce4-113">Parent Elements</span></span>

|<span data-ttu-id="bfce4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfce4-114">Element</span></span>|<span data-ttu-id="bfce4-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="bfce4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bfce4-116">Elemento EntrySelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="bfce4-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="bfce4-117">Define os tipos de .NET que usam essa entrada ou a condição que deve existir para essa entrada a ser usado.</span><span class="sxs-lookup"><span data-stu-id="bfce4-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bfce4-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="bfce4-118">Text Value</span></span>

<span data-ttu-id="bfce4-119">Especifique o nome do tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="bfce4-119">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="bfce4-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="bfce4-120">Remarks</span></span>

<span data-ttu-id="bfce4-121">Cada entrada da lista deve ter pelo menos um nome de tipo, conjunto de seleção ou condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="bfce4-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="bfce4-122">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="bfce4-122">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bfce4-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bfce4-123">See Also</span></span>

[<span data-ttu-id="bfce4-124">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="bfce4-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="bfce4-125">Elemento EntrySelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="bfce4-125">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="bfce4-126">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfce4-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
