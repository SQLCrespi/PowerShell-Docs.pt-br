---
title: Elemento TypeName para SelectionCondition para EntrySelectedBy para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b9367f0ea659b9dce8fe200a5a08873d53bc03a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772579"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="f382c-102">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f382c-102">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="f382c-103">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f382c-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="f382c-104">Quando esse tipo está presente, a condição é atendida e a linha da tabela é usada.</span><span class="sxs-lookup"><span data-stu-id="f382c-104">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="f382c-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element para EntrySelectedBy para TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f382c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f382c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f382c-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f382c-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f382c-107">Attributes and Elements</span></span>

<span data-ttu-id="f382c-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="f382c-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f382c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f382c-109">Attributes</span></span>

<span data-ttu-id="f382c-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f382c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f382c-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f382c-111">Child Elements</span></span>

<span data-ttu-id="f382c-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f382c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f382c-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f382c-113">Parent Elements</span></span>

|<span data-ttu-id="f382c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f382c-114">Element</span></span>|<span data-ttu-id="f382c-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="f382c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f382c-116">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f382c-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f382c-117">Define a condição que deve existir para esta linha de tabela ser usada.</span><span class="sxs-lookup"><span data-stu-id="f382c-117">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f382c-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f382c-118">Text Value</span></span>

<span data-ttu-id="f382c-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="f382c-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f382c-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="f382c-120">Remarks</span></span>

<span data-ttu-id="f382c-121">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="f382c-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="f382c-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f382c-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f382c-123">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f382c-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f382c-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f382c-124">See Also</span></span>

[<span data-ttu-id="f382c-125">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="f382c-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f382c-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="f382c-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f382c-127">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f382c-127">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f382c-128">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f382c-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f382c-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f382c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
